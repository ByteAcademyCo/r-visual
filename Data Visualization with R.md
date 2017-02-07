Data Visualization with R 
==================

Brought to you by [Lesley Cordero](http://www.columbia.edu/~lc2958).

## Table of Contents

- [0.0 Setup](#00-setup)
	+ [0.1 R and R Studio](#01-r-and-r-studio)
	+ [0.2 Packages](#02-packages)
- [1.0 Plotting Basics](#10-plotting-basics)
	+ [1.1 Plot Frames](#11-plot-frames)
	+ [1.2 Labels](#12-labels)
- [2.0 ggvis](#20-ggvis)
- [3.0 ggplot2](#30-ggplot2)
- [4.0 Heatmaply](#40-heatmaply)
- [5.0 plotly](#50-plotly)
- [6.0 Final Words](#60-final-words)
	+ [6.1 Resources](#61-resources)


## 0.0 Setup 

This guide was written in R 3.2.3.


### 0.1 R and R Studio

Download [R](https://www.r-project.org/) and [R Studio](https://www.rstudio.com/products/rstudio/download/).


### 0.2 Packages

To install the R packages, `cd` into your workspace, and enter the following, very simple, command into your bash: 

```
R
```

This will prompt a session in R! From here, you can install any needed packages. For the sake of this tutorial, enter the following into your terminal R session:

```
install.packages("ggvis")
install.packages("heatmaply")
install.packages("png")
```


## 1.0 Plotting Basics


### 1.1 Plot Frames


Visualizations are created on plot frames. To initialize a plot frame, you can write the following:

``` R
plot.new()
```
or 
``` R
frame()
```

Now, if you want to customize the sizes of a plotframe, you can do so as follows:

``` R
pWidth = 3
pHeight = 2
plot.window(c(0,pWidth),
            c(0,pHeight))
```

### 1.2 Labels

As with any visualization, you're going to want to attach labels:

``` R
mtext("x-axis", 
      side=1) #Add text to the x-axis
mtext("y-axis",
      side=2) 
title("An R Plot") #Add a title 
```

You might also want to add a box frame for the visualizations with: 

``` R
box()
```

### 1.3 Background

The default background is to have a plain white background. But that doesn't have to be the case. 

#### 1.3.1 Grids

For some purposes, you might find it necessary to include a grid in your plot. You can easily add a grid to your plot by using the `grid()` function. For example, as follows:

``` R
x <- c(1,2,3,4,5)
y <- 2*x
plot(x,y)
grid(10,10)
````

#### 1.3.2 Images

More exciting though, is the fact that you can make the background an image of your choice. In this example, I'll use the `png` module to put the Byte Academy logo as the background. 

``` R
library(png)
```

First, you want to load in the image. Use the `readPNG()` function to specify the path to the picture:

``` R
image <- readPNG("./byte.png")
```

Next, you want to set up the plot area and call the `par()` function:

``` R
plot(1:2, type='n', main="Plotting Over an Image", xlab="x", ylab="y")
lim <- par()
```

You can use the `par()` function to set the graphical parameters in `rasterImage()`. You use the argument `usr` to define the extremes of the user coordinates of the plotting region. In this case, you put 1, 3, 2 and 4:

``` R
rasterImage(image, lim$usr[1], lim$usr[3], lim$usr[2], lim$usr[4])
```

Next, you draw a grid and add some lines:

``` R
grid()
lines(c(1, 1.2, 1.4, 1.6, 1.8, 2.0), c(1, 1.3, 1.7, 1.6, 1.7, 1.0), type="b", lwd=5, col="red")
```

And there you have it! 

## 2.0 ggvis

[ggvis](http://ggvis.rstudio.com/) allows you to visualize interactive plots from the makers of ggplot2.

``` python
library(ggvis)
iris %>% ggvis(~Petal.Length, ~Petal.Width, fill = ~Species) %>% layer_points()
```

## 3.0 ggplot2

[ggplot2](http://www.statmethods.net/advgraphs/ggplot2.html) is one of the best static visualization packages in R. 

``` python
ggplot(mpg, aes(displ, 1 / hwy)) +
  geom_point() + 
  geom_smooth(method = lm, aes(colour = "lm"), se = FALSE) + 
  geom_smooth(aes(colour = "loess"), se = FALSE)
```


## 4.0 heatmaply

[heatmaply](https://mran.revolutionanalytics.com/package/heatmaply/) produces interactive heatmaps.

``` python
library(heatmaply)
heatmaply(cor(mtcars), 
  k_col = 2, k_row = 2,
  limits = c(-1,1)) %>% 
  layout(margin = list(l = 40, b = 40))
```

## 5.0 plotly

[plotly](https://plot.ly/r/) allows you to convert ggplot2 figures to interactive plots easily.

## 6.0 Final Words


### 6.1 Resources



