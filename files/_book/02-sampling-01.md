# Sampling {#sampling}

Sampling is the process of selecting a subset of elements from a larger population of elements, in order to study or analyze the properties of the subset. Sampling is a common technique used in statistics, research, and other fields, where it is often impractical or infeasible to study the entire population of elements. Instead, by selecting a representative sample of the population, researchers can study the sample and make inferences about the properties of the population as a whole.

Different types of sampling methods can be used to select a sample from a population, depending on the goals and constraints of the study. For example, random sampling is a method where each element in the population has an equal probability of being selected for the sample. Stratified sampling is a method where the population is divided into different groups or strata, and a representative sample is selected from each group. Cluster sampling is a method where the population is divided into different clusters or groups, and a sample is selected from each cluster.

Sampling can be an effective way to study a population of elements and to make inferences about the properties of the population. By selecting a representative sample of the population, researchers can study the sample and make statistical estimates or other inferences about the population as a whole. However, it is important to carefully design and implement the sampling process in order to ensure that the sample is representative of the population and that the inferences made from the sample are valid and accurate.

## Random sampling
In our course, we will mainly focus on random sampling. Random sampling is a method of sampling where each element in the population has an equal probability of being selected for the sample. Random sampling is a widely used method in statistics, research, and other fields, where it is often important to select a representative sample of a population in an unbiased and objective manner.

There are many different examples of how random sampling can be used in statistics, research, and other fields. Some common examples of random sampling include:

* Surveys and polls: Random sampling is often used in surveys and polls, where it is important to select a representative sample of a population in order to make inferences about the attitudes, opinions, or behaviors of the population as a whole. By using random sampling, researchers can ensure that the sample is selected in an unbiased and objective manner and that the sample is representative of the population.

* Clinical trials: Random sampling is commonly used in clinical trials, where it is important to select a representative sample of patients in order to evaluate the effectiveness of a new treatment or intervention. By using random sampling, researchers can ensure that the sample of patients is selected in an unbiased and objective manner and that the sample is representative of the population of patients who could potentially benefit from the treatment.

* Social experiments: Random sampling is often used in social experiments, where it is important to select a representative sample of individuals or groups in order to study the effects of a particular treatment or intervention. By using random sampling, researchers can ensure that the sample is selected in an unbiased and objective manner and that the sample is representative of the population of individuals or groups who could potentially be affected by the treatment.

These are just a few examples of how random sampling can be used in different contexts. There are many other examples of random sampling, and the specific applications and methods used will vary depending on the goals and constraints of the study. However, in all of these examples, random sampling is a useful technique for selecting a representative sample of a population and for making inferences about the population based on the sample.

## Coin flipping
Coin flipping is a form of random sampling because it is a simple and unbiased way of selecting one of two options, such as heads or tails. In statistics, random sampling is the process of selecting a subset of observations from a larger population in such a way that each member of the population has an equal probability of being chosen. Coin flipping is a random sampling method because it satisfies this criteria: each time a coin is flipped, there is a 50% probability of it landing on heads and a 50% probability of it landing on tails, regardless of any previous flips. This makes it a useful tool for generating random samples in statistical analysis.

### Coin flip in R
Let coin flip using R. To create a vector that contains the values "head" and "tail" in random locations, you can use the sample() function in R. Here is an example of how to do this:
  

```r
# create a vector of the values "head" and "tail"
coin_flip <- c("head", "tail")

# shuffle the values in the vector
coin_flip <- sample(x = coin_flip, size = 1, replace = T)

# print the shuffled vector
print(coin_flip)
#> [1] "tail"
```

In this code, we first create a vector called coin_flip that holds the values "head" and "tail". We then use the sample() function to shuffle the values in this vector, which randomly rearranges them. Finally, we print the resulting vector to the R console to verify that the values have been shuffled.

Note that the sample() function will always generate a different result each time it is called, so the exact sequence of values in the resulting vector will vary depending on the random seed used by R. However, the vector will always contain the values "head" and "tail", just in a different order each time. You can use this technique to create a vector of randomly-ordered values for any purpose, such as simulating a coin flip or other random event.

Alternatively, you can code as:

```r
sample(x = c("head", "tail"), size = 1, replace = T)
#> [1] "head"
```

## Rolling dice

Rolling dice is a form of random sampling because it is a simple and unbiased way of selecting a number from a set of possible values. Rolling dice is a random sampling method because it satisfies this criterion: each time a die is rolled, there is an equal probability of it landing on any of the possible values (e.g., 1, 2, 3, 4, 5, or 6 for a standard six-sided die), regardless of any previous rolls. This makes it a useful tool for generating random samples in statistical analysis.

### Dice roll in R

To simulate rolling a die in R, you can create a vector that holds the values 1 through 6 and then uses the sample() function to shuffle the values in this vector. Here is an example of how to do this:

```r
# create a vector of the values 1 through 6
dice <- 1:6

# shuffle the values in the vector
dice <- sample(dice, size = 1, replace = T)

# print the shuffled vector
print(dice)
#> [1] 3
```

In this code, we first create a vector called dice that holds the values 1 through 6. We then use the sample() function to shuffle the values in this vector, which randomly rearranges them. Finally, we print the resulting vector to the R console to verify that the values have been shuffled.

As with the previous example, the sample() function will generate a different result each time it is called, so the exact sequence of values in the resulting vector will vary depending on the random seed used by R. However, the vector will always contain the values 1 through 6, just in a different order each time. You can use this technique to simulate rolling a die or other random event that involves a set of values.

## Additional arguments in sample()
The sample() function in R has two optional arguments: size and replace. The size argument specifies the number of values to be returned by the function, while the replace argument specifies whether the sampling should be done with or without replacement. Here is an example of how to use these arguments:
  

```r
# create a vector of the values 1 through 6
dice <- 1:6

# shuffle the values in the vector with replacement, returning 3 values
dice <- sample(dice, size = 3, replace = TRUE)

# print the shuffled vector
print(dice)
#> [1] 5 3 2
```

In this code, we first create a vector called dice that holds the values 1 through 6. We then use the sample() function to shuffle the values in this vector, using the size and replace arguments to specify that we want 3 values to be returned, and that the sampling should be done with replacement. This means that the same value can be returned multiple times in the resulting vector. Finally, we print the resulting vector to the R console to verify that the values have been shuffled and that the size and replacement arguments have been applied correctly.

If we had omitted the replace argument or set it to FALSE, the sample() function would have returned a vector of values that were randomly shuffled, but without replacement. This means that each value would only appear once in the resulting vector, and no value would be repeated. For example, in standard 52 cards, if the first value returned by the sample() function was "3 of Spades", then the remaining 2 values would not be "3 of Spades", but some other cards from the deck.

The size and replace arguments can be useful for controlling the behavior of the sample() function and for generating specific types of random samples. For example, you could use the size argument to simulate drawing a certain number of cards from a deck, or to simulate rolling a certain number of dice. Similarly, you could use the replace argument to specify whether the sampling should be done with or without replacement, depending on the specific application.


## Exercises
> E1. Show R codes to simulate sum of the roll two standard six-sided dice.

> E2. Show R codes to draw 7 cards from a deck of 52 standard playing cards **with** and **without** replacement.
