---
title: Scatter Plots
author: Andrew Gehman
date: '2017-12-16'
slug: scatter-plots
categories:
  - Scatter Plots
tags:
  - Scatter Plots
  - plot
  - R Markdown
  - regression
---

If one would like to find the career strikeouts versus homeruns for great hitters within the baseball world, they can make a scatterplot to show the data found. One can do this using R code, like so.

First we must load the necessary packages:
```
library(Lahman)
library(sqldf)
library(devtools)
library(ggplot2)
```
Then we must extract the data:
```
query<-"SELECT playerID,sum(HR) AS career_HR,
sum(SO) AS career_SO FROM Batting 
GROUP BY playerID HAVING sum(HR)>=400"

result<-sqldf(query)

#visualizing data

ggplot()+
  geom_point(data=result,aes(x=career_SO,y=career_HR), size=1,color="green")+
  ggtitle("Career Strikeouts v. Homeruns for Great Hitters")+
  xlab("Career Strikeouts")+
  ylab("Career Homeruns")
```

![](https://hutton.netlify.com/post/2017-10-10-scatter-batter_files/figure-html/unnamed-chunk-2-1.png)

  