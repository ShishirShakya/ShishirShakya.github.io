---
title       : Quiz-2
subtitle    : Quick ggplot2
author      : 
job         : Use the left and right arrows to move backward or forward
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap, quiz] # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides

---
## Package ggplot2

To represent data visuallywe need following arguments: *dataset, coordinates the system and geoms (visual marks)*. Then we can enrich the visual experience by augmenting *aesthetics* such as the size, color, *statistics* (when required), *positioning*, *scaling* and *facets*. 

Before, we begin we have to understand the types of variables. There are two broad types of variables: **categorical** and **quantitative**. (I assume you know basic properties of these variables). For visual representation we can have few possible scenarios:

> One variable cases

> More than one variable cases

--- &radio
## Question 1: One categorical variable case

Suppose, you have a categorical variable (which may have more than two factors and may or may not have ordinal properties). What is the best plot for this case?

1. _barplot_
2. histogram
3. dotplot
4. areaplot
5. frequency polygon
6. qq plot

*** .hint
Example: 500 people were asked what is your favorite color? The response to this question is an example of a categorical variable.

--- &radio
## Question 2: One quantitative variable case



Suppose, you have a quantitative variable (which may discrete or continuous). What is **not** the best plot for this case?

1. _barplot_
2. histogram
3. dotplot
4. areaplot
5. frequency polygon
6. qq plot

*** .hint
You can always search in google for the meaning of each plot.


--- &radio
## Question 3: One quantitative variable cases

What is the name of a plot that can check the validity of distributional assumptions of univariate quantitative data?

1. barplot
2. histogram
3. dotplot
4. areaplot
5. frequency polygon
6. _qq plot_
7. density plot

*** .hint
You can always search in google for the meaning of each plot. 

---  &checkbox
## Question 4: Mix of categorical and quantitative variables

Suppose, you have the case of one quantitative variable and one categorical variable (with more than one factor) cases. Which type of plot is best for this situation?
Example: Which plot is best for plotting the blood pressure for those detected with and without obesity ?

---  &checkbox
## Question 5: Mix of quantitative variables

Suppose you have two (or more) quantitative variables. Which type of plot is best for this situation?

1. barplot, histogram, dotplot, areaplot, density, frequency polygon, qq plot but with facets
2. boxplot, violin plot
3. _scatter plot, density2d_
4. ribbon plot
5. Option 1 and 2
6. Option 3 and 4

*** .hint
Example: Which plot is the best for the daily average returns of S&P 500 and DJI?


---  &checkbox
## Question 6: Three quantitative variables

Suppose, you have three quantitative variables. Which type of plot is best for this situation?

1. barplot, histogram, dotplot, areaplot, density, frequency polygon, qq plot but with facets
2. boxplot, violin plot
3. scatter plot, density2d
4. contour plot
5. Option 1 and 2
6. _Option 3 and 4_

*** .hint
Example: Which plot is the best for the daily average returns of S&P 500, DJI and Apple?

---  &checkbox
## Question 7: Two categorical variables

Suppose, you have two categorical variables (each can have 2 or more factors). Which type of plot is best for this situation?

1. bar plot
2. stack plot
3. multiple plot
4. percentage stack plot
5. _All_
6. except percentage stack plot

*** .hint
Example: When asked which color they like, 210 people answered Red, 190 answered Blue and the rest answered another color.
