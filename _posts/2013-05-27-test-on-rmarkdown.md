---
published: true
status: publish
layout: post
title: "Test On RMarkdown"
description: ""
category: 
tags: []
---
{% include JB/setup %}
 
## The Normal Distribution
 
Firstly I will give a normal distribution listed as follows:
 
$$
f(x;\mu,\sigma^2) = \frac{1}{\sigma\sqrt{2\pi}} e^{ -\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2 }
$$
 
Then I try to plot it with R:
 

    output <- rnorm(1000, 100, 15)


    ggplot2::qplot(output)

    ## stat_bin: binwidth defaulted to range/30. Use 'binwidth = x' to adjust
    ## this.

![plot of chunk block2](/images/figure/block2.png) 

 
## 其他测试,中英文一起上

    summary(cars)

    ##      speed           dist    
    ##  Min.   : 4.0   Min.   :  2  
    ##  1st Qu.:12.0   1st Qu.: 26  
    ##  Median :15.0   Median : 36  
    ##  Mean   :15.4   Mean   : 43  
    ##  3rd Qu.:19.0   3rd Qu.: 56  
    ##  Max.   :25.0   Max.   :120


    plot(cars)

![plot of chunk unnamed-chunk-2](/images/figure/unnamed-chunk-2.png) 

