---
title       : Developing Data Products - Course Project
subtitle    : Wine Finder Shiny App
author      : Amber Beasock
framework   : revealjs
highlighter : highlight.js
hitheme     : default   
widgets     : []        
mode        : selfcontained 
knit        : slidify::knit2slides
---

## Developing Data Products  
### Course Project
Amber Beasock <br>
06MAR2016

---- 

## Summary
This presentation is the second part of the course project for the Coursera Developing Data Products course. The first part of the project was to develop a shiny application and deploy it on Rstudio's shiny server. The second part was to create a reproducible pitch presentation using Slidify or Rstudio Presenter and push the presentation to GitHub or Rpubs. <br> <br>
The shiny app developed for the first part of the assignment has been deployed on [shinyapps.io](https://amberbeasock.shinyapps.io/project_app/) <br> <br>
Source code for ui.R and server.R files on my [GitHub](https://github.com/abeasock/Developing_Data_Products-Coursera)

---- 

## The Shiny Application
An application called Wine Finder has been developed to help a user select a wine, using data collected from a leading wine source for ratings and reviews. <br> <br>

The user must select a wine type, region, and price range, and then hit "Submit". This information is used to calculate an average price of the selected wine type in the selected region and the average points of the selected wine type in the selected region within the selected price range. It also provides a table of wines filtered by the user's selected criteria. 

---

## The Data

The data was extracted from a leading wine website for ratings and reviews. Data was collected for four wine varietals (types): Cabernet Sauvignon, Chardonnay, Riesling, and Zinfandel. <br>
<br>

The variables included in this table:

- **varietal** - Wine type
- **title** - Brand dame
- **excerpt** - Brief description of wine 
- **points** - Wine Spectator 100-Point Scale
- **price** - Price
- **location** - Vineyard location
- **region** - Locations grouped into broader regions (ie. country)

---

## The Data Cont'd

Below is 10 random rows from the dataset. The title and excerpt columns are excluded due to limited space on the slide.
<br> 


```r
wine <- read.csv("wine_reviews.csv")[,c('varietal','region',
                                        'location','price','points')]
wine[sample(nrow(wine),10), ] # Random 10 rows to show variety
```

```
##                varietal        region       location price points
## 1502 Cabernet Sauvignon United States   Finger Lakes    23     86
## 968  Cabernet Sauvignon United States  Central Coast    40     84
## 6602           Riesling United States   Finger Lakes    39     94
## 2132 Cabernet Sauvignon United States     Washington    15     86
## 7412           Riesling       Germany        Germany    36     93
## 7303           Riesling       Austria        Austria    28     90
## 4970          Zinfandel United States Central Valley    10     84
## 4279          Zinfandel United States          Texas    44     85
## 4200          Zinfandel United States Central Valley    16     87
## 1703 Cabernet Sauvignon        Africa   South Africa    41     91
```
