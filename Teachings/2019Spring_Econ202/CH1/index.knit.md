---
title       : Quiz-1
subtitle    : Test your ability to import data and understand data structure
author      : 
job         : Use the left and right arrows to move backward or forward
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap, quiz] # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides

--- &radio
## Question 1

Suppose you downloaded the data `crime.cvs` and saved that in folder called `MyViz` in `D` drive. How can you set up the working directory in R?

1. setwd("D:/MyViz/crime.csv")
2. setwd(D:/MyViz)
3. _setwd("D:/MyViz")_
4. setwd(D:\MyViz)
5. setwd()

*** .hint
You can copy and paste these commands in your R environment to see the results.

*** .explanation
Make sure you use forward slash and quotation mark.

---  &checkbox
## Question 2
Which of the following commands can import the dataset into the R environment? (Suppose you downloaded the data `crimeData_Beginner.cvs` and saved the data in the "MyViz" folder of the D drive.)

1. read.csv("D:/MyViz/crime.csv")
2. crimedata = read.csv("D:/MyViz/crime.csv")
3. setwd("D:/MyViz"); crimedata = read.csv("crime.csv")
4. _All options are correct._ 
*** .hint
There are multiple correct answers.

---  &multitext

## Question 3
Please write down your answers. Please write your answer without any spaces.

1. How many observations are there in `crime.csv` dataset?
2. How many variables are there in `crime.csv` dataset?

*** .explanation

1. <span class='answer'>303467</span>
2. <span class='answer'>12</span>

*** .hint

Use command dim or see the Environment pane (if you are using RStudio.)

---  &checkbox
## Question 4
Suppose you load the crime.csv dataset and named it `crimedata`. Now use the command called `str()`. This command gives the dimensions of the dataset and the structure of each variable of the dataset. Generally, there are two broad types of variables a) categorical and b) numerical. 

Which of the following variables are not categorical variables?

1. ID
2. CNTYFIPS
3. Month
4. Year
5. Weapon
6. _VicAge_

*** .hint
Some variables are expressed as integers, but they are actually categorical.

---  &multitext

## Question 5
Please write down your answers. Please write your answer without any spaces. Use the function `summary(crimedata)`.

1. How many cases are unsolved?
2. How are the missing values for the age of victims recorded in this dataset?


*** .explanation

1. <span class='answer'>93007</span>
2. <span class='answer'>998</span>

*** .hint
Avoid writing the decimal in the answer.

--- &checkbox
## Question 6

How do you install several packages, such as `ggplot2`, `ggvis` and `dplyr`, at once?

1. install.packages("ggplot2");install.packages("ggvis"); install.packages("dplyr")
2. install.packages(c("ggplot2", ggvis","dplyr"))
3. Packages cannot be installed in R.
4. _Option 1 and Option 2 both works_

---
## Verbs of dplyr package
Package `dplyr` is the major package for data manipulation and transformation. Most of the data manipulation can be implemented with dplyr's `6 major verbs`. 

1. `summarise` to summarize the selected data
2. `group_by` to create a grouped copy of the table.
3. `filter` to filter the data to select specific rows.
4. `arrange` to arrange the data into an order.
5. `select` to select a specific column.


---
## Piping **%>%** of the magrittr R package

**The pipe function** `%>%` of the magrittr R package transfers the output of one function to the next function. You can consider `%>%` to pronounce  **then**. In R studio, you can press `Ctrl+Shit+M` to pipe (in Windows) `Cmd+Shit+M` in Mac. For more information, see the help file `?magrittr::`%>%``. 

**Example:** Suppose, you want to arrange the case counts in ascending order based on how many cases were solved and unsolved by the victim's gender.  

crimedata = read.csv("D:/MyViz/crime.csv")
library(dplyr)

* Method-1 (General)

> tally(group_by(crimedata, Solved, VicSex), sort = T)

* Method-2 (Piping)

> crimedata %>% group_by(Solved, VicSex) %>% tally(sort=T)

Take data called `crimedata` `%>%` **then** `groupby` with case and victim's gender **then** `tally`.

--- &radio
## Question 7

Take the crimedata, `group_by` `Month` and `Homicide`, then `tally` and `View`. Which month have highest *Manslaughter by negligence* and *Murder and non-negligent manslaughter* frequency?

1. Jan and Jul
2. Jun and Aug
3. Dec and Jan
4. _Jul and Jul_

*** .hint
`crimedata %>% group_by() %>% tally() %>% View()`

--- &radio
## Question 8

Now, filter the unresolved cases then group by Months and Homicide cases and tally and view. Which month have the pile of unresolved cases on
Murder and non-negligent manslaughter?

1. Jan
2. Feb
3. Dec
4. _Jul_

*** .hint
`filter(Solved==) %>% group_by(,)  %>% tally(sort=T)`

--- &radio
## Question 9

What is the age of the oldest victim at Wyoming whose case has not yet been solved? First run this code: `crimedata$VicAge[crimedata$VicAge == 998] <- NA`

1. 99
2. _64_
3. 998
4. 66

*** .hint
.... `%>% summarise(max())%>%` ...

--- &radio
## Question 10

What is the case ID of the oldest unresolved case at West Virginia?

1. _353874_
2. 353918
3. 353938
4. 353889

*** .hint
`crimedata %>% filter(State=="" & Solved == "" & Year == )  %>% View()`
