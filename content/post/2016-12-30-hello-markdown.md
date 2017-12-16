---
title: "Bar Plots"
date: "2016-12-30T21:49:57-07:00"
---

Here I will explain how to create bar plots in R Studio using the Lahman Baseball Package as an example. 

First we must load the libraries:

```
library(Lahman)
library(sqldf)
library(devtools)
library(ggplot2)
``` 

Next, we must extract the data. 
```
query<-"SELECT name,HR FROM Teams WHERE yearID=1980
ORDER BY HR"
result<-sqldf(query)

result$name<-factor(result$name,levels=result$name)


ggplot()+
  geom_bar(data=result,aes(x=name,y=HR),stat='identity',
           color='blue',fill='black')+
  coord_flip()+
  xlab("Team Name")+
  ylab("Homeruns")+
  ggtitle("1980 Team Homerun Distribution")
```   

![](https://hutton.netlify.com/post/2017-10-10-bar-plot_files/figure-html/unnamed-chunk-2-1.png)

