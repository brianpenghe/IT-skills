---
title: 'How to plot a forest plot/ treemap using R'
date: 2016-02-22T18:02:00.000-08:00
draft: false
url: /2016/02/how-to-plot-forest-plot-treemap-using-r.html
---

> **Archived note — originally created: 2016-02-22 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


data <- read.csv("http://datasets.flowingdata.com/post-data.txt") 
install.packages("portfolio") 
**library(grid)** 
**library(lattice)** 
**library(nlme)** 
library(portfolio) 
map.market(id=data$id, area=data$views, group=data$category, color=data$comments, main="FlowingData Map") 

# Attention:the data file shouldn't contain tabs; the first row has to have the column names; the color code value range is between around -50 to 50; the local file path shouldn't have \\ but / ; have fun 

reference:https://flowingdata.com/2010/02/11/an-easy-way-to-make-a-treemap/

#R #TroubleshootNotes #BloggerPublishedNonAcademicNotes
