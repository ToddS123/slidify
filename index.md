---
title: "Boxplot Selection Feature Tool"
author: "Todd S"
highlighter: highlight.js
output: pdf_document
job: Analyst
knit: slidify::knit2slides
mode: selfcontained
hitheme: tomorrow
subtitle: R mtcars Dataset analysis
framework: io2012
widgets: []
---

## Introduction

The Boxplot Selection Feature Tool was constructed to streamline the assessment of variable analysis of the R mtcars dataset.  The tool provides a simple to use interface to select three different variables to assess their impact on miles per gallon.  

The tool displays a visual output of the variables using a boxplot as well as a table output of the raw data being compared.  The tool includes the ability to customize the boxplot output including changing color, shape, direction and font size.

--- .class #id 

## Advantages and Limitations

Advantages of the tool

1. Variables of the mtcars dataset can be compared to MPG without writing any R Code

2. The Boxplot visual output can be easily customized without writing any R Code

3. The selected variable output is displayed in a boxplot and table output comparing to MPG

Limitations of the tool

1. Only three of the variables from the MTCars dataset are avaiable for analysis

2. Only the MPG (miles per gallon) variable is used to compare variables

--- .class #id 

## Data Summary

The variables avaiable to assess within the tool are:  cyl,am,gear.

```r
head(mtcars,n=1)
```

```
##           mpg cyl disp  hp drat   wt  qsec vs am gear carb
## Mazda RX4  21   6  160 110  3.9 2.62 16.46  0  1    4    4
```
The tool compares the mpg mean for each level of the selected varaible.  The cyl variable is outlined below as an example:

```r
aggregate(mpg~cyl, mtcars,mean)
```

```
##   cyl      mpg
## 1   4 26.66364
## 2   6 19.74286
## 3   8 15.10000
```


--- .class #id 

## Boxplot output view sample


```r
boxplot(mpg~cyl, 
        data = mtcars,
        outline = TRUE,          #outliers
        col = "green",               #color
        notch=FALSE,              #notch style
        horizontal=FALSE,         #Directions
        cex.lab=2)               #Font Size of the axis label
```

![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3-1.png)




