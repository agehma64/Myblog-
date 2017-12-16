---
title: "Histograms"
date: 2015-01-01T13:09:13-06:00
---

When you have one column of data and want to see how the data is spread out, you would use a histogram. First you load the libraries:

```
library(Lahman)
library(sqldf)
library(ggplot2)
```

```
query<-"SELECT weight FROM Master"

result<-sqldf(query)

ggplot()+

geom_histogram(data=result,aes(x=weight),color="blue",fill="yellow",bins=50)+

ggtitle("Body-Weight Distribution for Baseball Players")
```
  
![Histogram](https://hutton.netlify.com/post/2017-10-10-histogram_files/figure-html/unnamed-chunk-2-1.png)  