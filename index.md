---
title       : impress.js
subtitle    : Testing impress.js with Slidify
author      : Stephen
job         : researcher
framework   : impressjs       # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : zenburn     # {tomorrow, zenburn}
widgets     : mathjax            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
logo        : []
url         : []
--- .class #1



## Testing Impress.js 

Using **slidify** in <b>R</b>


--- .class #2 x:3000 y:0 scale:2

## Regular plotting


```r
x <- rnorm(1000,0,5)
plot(cumsum(x),main="Gaussian Walk",col='red',
     ylab=expression(Sigma[t]*x[t]),
     xlab='t',type='l')
abline(h=0,col='black')
```

![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2.png) 

--- .class #3 x:0 y:-2000 scale:2 rot:45

## GGPLOT2

![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3.png) 

--- .class #4 x:-2000 y:-2000 scale:1 rot:-45

## Do a Unit Root Test


```r
adft <- adf.test(x = cumsum(x),alternative = 'stationary')
print(adft)
```

```
## 
## 	Augmented Dickey-Fuller Test
## 
## data:  cumsum(x)
## Dickey-Fuller = -3.02, Lag order = 9, p-value = 0.1465
## alternative hypothesis: stationary
```

--- .class #5 x:3000 y:-4000 scale:4 rot:180

## Formulae with MathJax

  1. **$Y=X\beta + \epsilon$**
  2. $\frac{-\beta \pm \sqrt{\beta^2-4\alpha\gamma}}{2\alpha}$

--- .class #6 x:2000 y:3000 scale:2 rot:-180

## iGraph


```r
g <- barabasi.game(n = 20, power = 1.1, m = 3, directed = T)
par(mar=c(.5,.5,2.2,.5))
plot.igraph(g, layout=layout.fruchterman.reingold,
            vertex.size=degree(g)*2,edge.arrow.size=.5,
            edge.color='dark gray',vertex.color='dark blue',
            vertex.label.color='white',
            main="Preferential Attachment Model\nBarabasi Random Graph")
```

--- .class #7 x:-3000 y:2000 scale:8

## iGraph

![plot of chunk unnamed-chunk-6](assets/fig/unnamed-chunk-6.png) 
