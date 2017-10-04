---
title       : Developing Data Product - Assignment 2
subtitle    : Using Slidify and Plotly
author      : Prasath and Date 10/4/2017
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
--- 

## R Code 

```r
suppressMessages(library(plotly)) 
suppressMessages(library(tidyr)) 
suppressMessages(library(dplyr))
data("EuStockMarkets")
stocks <- as.data.frame(EuStockMarkets) %>%
  gather(index, price) %>%
  mutate(time = rep(time(EuStockMarkets), 4))
plot_ly(stocks, x = ~time, y = ~price, color = ~index, type = "scatter", mode = "lines")
```

```
## Error in loadNamespace(name): there is no package called 'webshot'
```

--- 

<iframe src="plot.html"
        height="200" width="30%"
        scrolling="no" seamless="seamless"
        frameBorder="0">
</iframe>

