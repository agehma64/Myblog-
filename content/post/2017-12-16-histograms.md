---
title: 'Histograms '
author: Andrew Gehman
date: '2017-12-16'
slug: histograms
categories:
  - Histograms
tags:
  - Histograms
  - R Markdown
  - plot
---

First we must load the necessary packages.
```
library(Lahman)
library(sqldf)
library(ggplot2)
```

Then we must extract the data in order to get our final results.

```
query<-"SELECT weight FROM Master"

result<-sqldf(query)

#visualizing the data

ggplot()+
  geom_histogram(data=result,aes(x=weight),color="blue",fill="yellow",bins=50)+
  ggtitle("Body-Weight Distribution for Baseball Players")
```
![](https://hutton.netlify.com/post/2017-10-10-histogram_files/figure-html/unnamed-chunk-2-1.png)