# Census Bureau ongoing external projects

This repository captures various versions of the data on external projects in the Federal Statistical Data Centers (FSRDC). The data is captured at this time manually, by identifying files as they are released.

## Original description

> At Federal Statistical Research Data Centers (FSRDCs), researchers use restricted-access microdata to address important research questions.  An Excel spreadsheet containing metadata about active and completed projects, including project title, abstract, FSRDC location, principal investigator, year project started, researchers, and datasets requested in project proposals is available for download below. 
> 
> Currently metadata is only provided for projects that solely use Census Bureau datasets. Project information will be updated quarterly.

## Versions 

The latest version is linked from [https://www.census.gov/about/adrm/fsrdc/about/ongoing-projects.html](https://www.census.gov/about/adrm/fsrdc/about/ongoing-projects.html). The following versions have been identified:

- 2021Q1: [ProjectsAllMetadata_09APR2021.xlsx](https://www.census.gov/content/dam/Census/about/about-the-bureau/fsrdc/documents/ProjectsAllMetadata_09APR2021.xlsx)
- 2020Q4: [ProjectsAllMetadata_18DEC2020.xlsx](https://www.census.gov/content/dam/Census/about/about-the-bureau/fsrdc/documents/ProjectsAllMetadata_18DEC2020.xlsx) (via [20210325024735 capture](https://web.archive.org/web/20210325024735/https://www.census.gov/about/adrm/fsrdc/about/ongoing-projects.html))
- 2020Q3: [ProjectsAllMetadata_17SEP2020.xlsx](https://www.census.gov/content/dam/Census/about/about-the-bureau/fsrdc/documents/ProjectsAllMetadata_17SEP2020.xlsx) (via [20201101065600 capture](https://web.archive.org/web/20201101065600/https://www.census.gov/about/adrm/fsrdc/about/ongoing-projects.html))

Earlier ones are being obtained.

## Script

We ran this script, without success, to obtain earlier versions:

```{bash}
for day in $(seq 1 31)
do 
  [[ $day -lt 10 ]] && zday=0$day || zday=$day
  for month in JAN FEB MAR APR MAY JUN JUL AUG
  do 
      name=ProjectsAllMetadata_${zday}${month}2020.xlsx
      wget https://www.census.gov/content/dam/Census/about/about-the-bureau/fsrdc/documents/$name
  done
done
```
