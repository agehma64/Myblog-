---
title: 'Time Series '
author: Andrew Gehman
date: '2017-12-16'
slug: time-series
categories: []
tags:
  - Time Series
  - plot
  - R Markdown
---

The x axis represents time, while the y is variable of your choice. First we load the libraries

```
library(Lahman)
library(sqldf)
library(devtools)
library(ggplot2)
```
Then we must extract the data, in order to get the time series. 

```
query<-"SELECT yearID,HR FROM Batting WHERE playerID='ruthba01'"

result<-sqldf(query)


ggplot()+
  geom_point(data=result,aes(x=yearID,y=HR),color="black")+
  geom_line(data=result,aes(x=yearID,y=HR),color="blue")+
  ggtitle("Ruth's Homerun Totals Through the Years")+
  xlab("Year")+
  ylab("Homeruns")
```

![](https://hutton.netlify.com/post/2017-10-10-time-series_files/figure-html/unnamed-chunk-2-1.png)
