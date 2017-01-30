Intro to R Programming
==================

Brought to you by [Lesley Cordero](http://www.columbia.edu/~lc2958).

## Table of Contents

- [0.0 Setup](#00-setup)
	+ [0.1 R and R Studio](#01-r-and-r-studio)
	+ [0.2 Packages](#02-packages)
- [1.0 Data Types and Operators](#10-data-types-and-operators)
	+ [1.1 Math and Numbers](#11-math-and-numbers)
	+ [1.2 Booleans and Equality](#12-booleans-and-equality)
	+ [1.3 Comparisons](#13-comparisons)
	+ [1.4 Strings](#14-strings)
	+ [1.5 Printing](#15-printing)
- [2.0 Control Flow](#20-control-flow)
	+ [2.1 If/Else](#21-if/else)
	+ [2.2 For Loops](#22-for-loops)
	+ [2.3 While Loops](#23-while-loops)
	+ [2.4 Try/Except](#24-try/except)
- [7.0 Final Words](#60-final-words)
	+ [7.1 Resources](#61-resources)
	+ [7.2 More!](#72-more)


## 0.0 Setup 

This guide was written in R 3.2.3.


### 0.1 R and R Studio

Download [R](https://www.r-project.org/) and [R Studio](https://www.rstudio.com/products/rstudio/download/).


### 0.2 Packages


```
install.packages("")
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

## 5.0 Final Words

### 5.1 Resources



