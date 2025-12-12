---
title: "A Bivariate Spatial Analysis"
excerpt: "Analysis of Internet and Household Income (2025) <br/><img src='/images/spatauto.png'>"
collection: portfolio
---

### Objective 
Is there a spatial relationship between internet subscription and median household income in Philadelphia, PA?

### Methods
**Data Retrieval and Preparation in R**
* Used ACS 5 year data to get variables by tract for those with any internet subscription, total in that category (incl those with no internet), and median household income
* Calculated percent with internet
* Used `erase_water()` from the `tigris` package to remove water bodies from the feature
* exported as shapefile for use in GeoDa

**GeoDa**
* Conducted a bivariate local Moran's i with median household income as the lagged variable
* Exported LISA results as a new shapefile for cluster mapping in QGIS

**QGIS**
* Symbolized by LISA cluster field and adjusted legend entries to reflect cluster meanings

### Results 
<br/><img src='/images/spatauto.png'>
* In the Philadelphia map, many tracts fall under Not Significant (variables change more
independently or randomly), but where clusters exist, most of them are very significant.
* There are several regions of significant clusters.
  Two of these show higher neigborhood median household income and higher rates of internet subscription:
    1. Northeast Philadelphia
    2. Center City
  
  Three other regions show primarily low NMHI and low internet.
    1. East & South of Wynnefield Avenue (West of Schuylkill River)
    2. A South West area mostly West along the Schuylkill River
    3. North Philadelphia towards Wayne Junction

*Geographical areas are approximate descriptions using an Open Street Maps basemap in QGIS.*

### Conclusions
1. Considering these regions of clusters (excluding areas of non significant
relationships), there is a general positive correlation between NMHI and internet
since many clusters are either high high or low low, and these clusters appear
together. This implies a large gap in income and internet access between distinct
geographical areas.
2. Low NMHI low internet regions (dark purple) contain or border low NMHI high
internet regions (light purple). This implies that there may be variable(s) driving a
difference in internet among low income areas, i.e. a reason why one area of low
income has internet access while an adjacent area has lower rates of internet.
Investigating this difference could be important if one is seeking solutions for
limits to internet access.
3. High income areas (bright orange) are rather geographically isolated from lower
income areas (both purple) emphasizing wealth gaps.
4. As would be expected, there are very few clusters identified as high NMHI and low
internet.
