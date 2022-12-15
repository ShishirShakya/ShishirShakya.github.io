# Data types, structures, and extractions

## Basic Mathematical operations
R provides built-in functions for performing basic mathematical operations, such as addition, subtraction, multiplication, and division. Here are some examples of R code that demonstrate how to use these functions:

* Addition: to add two numbers in R, use the + operator. For example, to add 2 and 3, you would write 2 + 3.
* Subtraction: to subtract one number from another in R, use the - operator. For example, to subtract 3 from 5, you would write 5 - 3.
* Multiplication: to multiply two numbers in R, use the * operator. For example, to multiply 2 and 3, you would write 2 * 3.
* Division: to divide one number by another in R, use the / operator. For example, to divide 10 by 2, you would write 10 / 2.
Here is an example of how you might use these operations in a simple R script:


```r
# define two variables
a <- 2
b <- 3

# add the variables
c <- a + b
print(c) # prints 5
#> [1] 5

# subtract the variables
d <- a - b
print(d) # prints -1
#> [1] -1

# multiply the variables
e <- a * b
print(e) # prints 6
#> [1] 6

# divide the variables
f <- a / b
print(f) # prints 0.6666667
#> [1] 0.6666667
```

In this code, we define two variables a and b and then perform the four basic mathematical operations on them. We then print the results of each operation to the R console to verify that they are correct. Note that R uses the standard order of operations, so multiplication and division are performed before addition and subtraction.

## Good versus bad names 
I copied this section from Hands-On Programming with R by Garrett Grolemund chapter 2 "The Very Basics" (https://rstudio-education.github.io/hopr/basics.html).

There is a naming convention in R. You can name an object in R almost anything you want, but there are a few rules. First, a name cannot start with a number. Second, a name cannot use some special symbols, like ^, !, $, @, +, -, /, or *.

Good name | Bad name
------------- | -------------
a | 	1trial
b	| $
FOO| 	^mean
my_var| 	2nd
.day| 	!bad

In R variable defined as "a" is not equal to "A". In other words, R is case-sensitive, so name and Name will refer to different objects:


```r
Name <- 1
name <- 0

Name + 1
#> [1] 2
name + 1
#> [1] 1
```

Finally, R will overwrite any previous information stored in an object without asking you for permission. So, it is a good idea to not use names that are already taken:


```r
my_number <- 1
my_number 
#> [1] 1

my_number <- 999
my_number
#> [1] 999
```

## Some additional mathematical operations
Now, let's get back to additional mathematical operations. R also provides functions for performing more advanced operations, such as exponentiation and square roots. These operations are performed using the ^ and sqrt() functions. Here are some examples of how to use these functions in R:

* Exponentiation: to raise a number to a power in R, use the ^ operator. For example, to raise 2 to the power of 3, you would write 2^3. This will compute 2 * 2 * 2, which is equal to 8.

* Square root: to compute the square root of a number in R, use the sqrt() function. For example, to compute the square root of 4, you would write sqrt(4). This will compute the square root of 4, which is equal to 2.
Here is an example of how you might use these operations in a simple R script:


```r
# define a variable
x <- 2

# compute x to the power of 3
y <- x^3
print(y) # prints 8
#> [1] 8

# compute the square root of x
z <- sqrt(x)
print(z) # prints 2
#> [1] 1.414214
```

In this code, we define a variable x and then use the ^ and sqrt() functions to perform exponentiation and square root operations. We then print the results of each operation to the R console to verify that they are correct. Note that when using the ^ operator, the number being raised to a power must be placed on the left side of the operator, and the power must be placed on the right side. Similarly, when using the sqrt() function, the number whose square root is being computed must be placed inside the parentheses.

In economics, the logarithm of a number is often used to represent the growth rate of a variable over time. This can be useful for analyzing economic phenomena such as inflation, GDP growth, and population growth. In R, the logarithm of a number can be computed using the log() function. Here is an example of how to use this function in R:


```r
# define a variable
x <- 100

# compute the natural log of x
y <- log(x)
print(y) # prints 4.60517
#> [1] 4.60517
```

In this code, we define a variable x and then use the log() function to compute the natural logarithm of x. We then print the result to the R console to verify that it is correct. The natural logarithm is the logarithm with base e, where e is a mathematical constant approximately equal to 2.71828.

R also provides the log10() function, which computes the logarithm with base 10. For example, to compute the logarithm with base 10 of 100, you would write log10(100), which would return 2 (since 100 = 10^2). The log() and log10() functions are commonly used in economics to analyze growth rates and other economic phenomena.

## Data types

In R, there are three main data types: integer, numeric, and character.

* Integer: an integer is a whole number, such as 1, 2, or 3. In R, integers are represented using the int data type. Here is an example of how to create an integer variable in R:


```r
# define an integer variable
x <- 1

# print the data type of x
class(x) # prints "integer"
#> [1] "numeric"
```

* Numeric: a numeric value is a decimal number, such as 1.5, 2.7, or 3.14. In R, numeric values are represented using the numeric data type. Here is an example of how to create a numeric variable in R:


```r
# define a numeric variable
x <- 1.5

# print the data type of x
class(x) # prints "numeric"
#> [1] "numeric"
```


* Character: a character value is a string of text, such as "hello" or "world". In R, character values are represented using the character data type and they are kept in between quote marks. Here is an example of how to create a character variable in R:

```r
# define a character variable
x <- "hello"

# print the data type of x
class(x) # prints "character"
#> [1] "character"
```

It is important to understand the different data types in R, as they determine how your data will be treated and what operations you can perform on it. For example, you cannot perform mathematical operations on character values, but you can concatenate them using the paste() function. Additionally, you must be careful to convert between data types when necessary, as R will not automatically do this for you. For instance, if you try to divide an integer by a numeric value, you will get an error unless you explicitly convert the integer to a numeric value first.


## Data structure
R programming language includes various data structures commonly used in statistical analysis and data science, including vectors, matrices, data frames, and lists.

* Vectors are one-dimensional data arrays that can hold numeric, character, or logical values.
* Matrices are two-dimensional data arrays that can hold numeric, character, or logical values.
* Data frames are two-dimensional arrays that can hold different data types in each column, similar to a spreadsheet.
* Lists are collections of objects that can hold various data types, including other lists.

These data structures are designed to make it easy to organize and manipulate data for statistical analysis and visualization.

### Atomic vector and extraction
In R, an atomic vector is a data structure that holds a single data type. All the values in an atomic vector must be of the same type, such as integer, numeric, or character. Here is an example of how to create an atomic vector in R:


```r
# create an atomic vector of integers
x <- c(1, 2, 3)

# print the data type of x
class(x) # prints "integer"
#> [1] "numeric"

# create an atomic vector of numeric values
y <- c(1.5, 2.7, 3.14)

# print the data type of y
class(y) # prints "numeric"
#> [1] "numeric"

# create an atomic vector of character values
z <- c("hello", "world")

# print the data type of z
class(z) # prints "character"
#> [1] "character"
```


In this code, we create three atomic vectors: x, which holds integer values; y, which holds numeric values; and z, which holds character values. We then use the class() function to print the data type of each vector, which shows that they are of the correct type. Note that we use the c() function to create an atomic vector, and we must pass in the values that we want to include in the vector as arguments to this function.

Atomic vectors are a fundamental data structure in R and are used in many different contexts. For example, they can be used to represent the columns of a data frame or the elements of a list. They are also used to hold the results of many R functions, such as statistical tests or regression models. Understanding how atomic vectors work is essential for working with data in R.

To extract the value "hello" from the atomic vector z, you can use the [] operator to index into the vector and retrieve the desired element. Here is an example of how to do this in R:


```r
# create an atomic vector of character values
z <- c("hello", "world", "anime")

# extract the first element of z
x <- z[1]

# print x
print(x) # prints "hello"
#> [1] "hello"
```

In this code, we create an atomic vector z that holds the values "hello" and "world". We then use the [] operator to extract the first element of z, which is "hello". We assign this value to the variable x, and then print x to verify that it has the correct value.

Note that in R, indexing starts at 1, so the first element of a vector is at index 1, the second element is at index 2, and so on. [] is that to extract the first element of z, we must use the index 1, not 0, as we might expect in some other programming languages. Additionally, the [] operator can be used to extract multiple elements from a vector by passing in a vector of indices as the index. For example, to extract the first and third elements of z, we could write x <- z[c(1, 3)], which would assign the values "hello" and "world" to x in that order.

To specify the exact value "hello" in the [] operator, you can use the which() function to find the index of "hello" in the vector z. Here is an example of how to do this in R:


```r
# create an atomic vector of character values
z <- c("hello", "world")

# find the index of "hello" in z
i <- which(z == "hello")

# extract the element at index i from z
x <- z[i]

# print x
print(x) # prints "hello"
#> [1] "hello"
```

In this code, we create an atomic vector z that holds the values "hello" and "world." We then use the which() function to find the index of "hello" in z. This function returns a vector of indices, so in this case, it will return the single value 1. We assign this value to the variable i, and then use i as the index to extract the element at that index from z. Finally, we print x to verify that it has the correct value.

Here is an example of how to extract elements from a numeric atomic vector in R:


```r
# define a numeric atomic vector
x <- c(1, 3, 5, 7, 9)

# extract the first element from the vector
print(x[1])  # prints 1
#> [1] 1

# extract the last element from the vector
print(x[length(x)])  # prints 9
#> [1] 9

# extract the second and third elements from the vector
print(x[2:3])  # prints 3 5
#> [1] 3 5

# extract the even-numbered elements from the vector
print(x[seq(2, length(x), 2)])  # prints 3 9
#> [1] 3 7
```

In this code, we define a numeric atomic vector x that contains the values 1, 3, 5, 7, and 9. We then use different indexing operators to extract different elements from the vector x.

For example, we use the [1] indexing operator to extract the first element from the vector x, which has the value 1. We use the [length(x)] indexing operator to extract the last element from the vector x, which has the value 9. We use the [2:3] indexing operator to extract the second and third elements from the vector x, which have the values 3 and 5. Finally, we use the seq() function and the [seq(2, length(x), 2)] indexing operator to extract the even-numbered elements from the vector x, which has the values 3 and 9.

This code demonstrates how to use different indexing operators to extract elements from a numeric atomic vector in R. By using these operators, you can select and manipulate specific elements of a vector, and you can use the extracted elements in further calculations or other operations.

### Matrix and extraction
A matrix is a data structure in R that allows you to store and manipulate data in a two-dimensional grid. Each element in a matrix is identified by its row and column indices and can be accessed using the [,] operator.

Here is an example of how you could create a matrix in R:


```r
# Define a matrix containing the values 1, 2, 3, 4, 5
matrix <- matrix(c(1, 2, 3, 4, 5, 6), nrow = 2, ncol = 3)
```

This code will create a matrix with 2 rows and 3 columns, containing the values 1, 2, 3, 4, 5. The matrix will be printed to the console, and will look like this:


```r
# Print the matrix
matrix
#>      [,1] [,2] [,3]
#> [1,]    1    3    5
#> [2,]    2    4    6
```

In this example, the matrix has 2 rows and 3 columns, and the values in the matrix are arranged in the grid according to their row and column indices. For example, the value 3 is located in the first row and second column of the matrix, and can be accessed using the [1,2] index.

To access an element in a matrix, you can use the [,] operator. Here is an example of how you could do this:


```r
# Print the element at the first row and second column of the matrix
matrix[1,2]
#> [1] 3

# Don't print the first element but print second column of the matrix
matrix[-1,2]
#> [1] 4

# Don't print the first element and second column of the matrix, but print all
matrix[-1,-2]
#> [1] 2 6

# Print first two rows and all columns
matrix[c(1,2), ]
#>      [,1] [,2] [,3]
#> [1,]    1    3    5
#> [2,]    2    4    6

# Don't print first two rows but print all the columns
matrix[-c(1,2), ]
#>      [,1] [,2] [,3]
```


Let's create a large matrix.

```r
# Define a matrix containing the values 1, 2, 3, 4, 5
large_matrix <- matrix(c(1:1000), nrow = 100, ncol = 10)
```

Now lets extract selected row from 2 to 7, then 89, and 99 for column 1 to 3 and 7.


```r
large_matrix[c(2:17,89,99), c(1:3, 7)]
#>       [,1] [,2] [,3] [,4]
#>  [1,]    2  102  202  602
#>  [2,]    3  103  203  603
#>  [3,]    4  104  204  604
#>  [4,]    5  105  205  605
#>  [5,]    6  106  206  606
#>  [6,]    7  107  207  607
#>  [7,]    8  108  208  608
#>  [8,]    9  109  209  609
#>  [9,]   10  110  210  610
#> [10,]   11  111  211  611
#> [11,]   12  112  212  612
#> [12,]   13  113  213  613
#> [13,]   14  114  214  614
#> [14,]   15  115  215  615
#> [15,]   16  116  216  616
#> [16,]   17  117  217  617
#> [17,]   89  189  289  689
#> [18,]   99  199  299  699
```

Matrix can only have one type of data type, either character or numeric. For this reasons, in our class, we will not use matrix a lot.

```r
# Define a matrix containing the values 1, 2, 3, 4, 5, A
matrix <- matrix(c(1, 2, 3, 4, 5, "A"), nrow = 2, ncol = 3)
matrix
#>      [,1] [,2] [,3]
#> [1,] "1"  "3"  "5" 
#> [2,] "2"  "4"  "A"
```


### Dataframe and extraction
A data frame is a data structure in R that allows you to store and manipulate tabular data. A data frame is similar to a matrix, but it can have different data types for its columns, and it can have row and column names.

Here is an example of how you could create a data frame in R:


```r
# Define a data frame containing the values 1, 2, 3, 4, 5
data_frame <- data.frame(x = c(1, 2, 3, 4, 5),
                         y = c("A", "B", "C", "D", "E"))
```

This code will create a data frame with 5 rows and 2 columns, containing the values 1, 2, 3, 4, 5. The columns in the data frame will be named "x" and "y", and the data frame will be printed to the console. It will look like this:


```r
# Print the data frame
data_frame
#>   x y
#> 1 1 A
#> 2 2 B
#> 3 3 C
#> 4 4 D
#> 5 5 E
```

In this example, the data frame has 5 rows and 2 columns, and the values in the data frame are arranged in a table according to their row and column names. Similar to matrix, we can use [,] operator. 


```r
# Print the element at the first row and second column of the data_frame
data_frame[1,2]
#> [1] "A"

# Don't print the first element but print second column of the data_frame
data_frame[-1,2]
#> [1] "B" "C" "D" "E"

# Don't print the first element and second column of the data_frame, but print all
data_frame[-1,-2]
#> [1] 2 3 4 5

# Print first two rows and all columns
data_frame[c(1,2), ]
#>   x y
#> 1 1 A
#> 2 2 B

# Don't print first two rows but print all the columns
data_frame[-c(1,2), ]
#>   x y
#> 3 3 C
#> 4 4 D
#> 5 5 E
```

You can see we can almost extract the elements like in matrix. However there is even a better approach. For example, the value 3 is located in the third row and "x" column of the data frame, and can be accessed using the data_frame$x[3] index.

To access an element in a data frame, you can use the $ operator to access a column, and the [,] operator to access a row. Here is an example of how you could do this:


```r
# Print the value at the third row and "y" column of the data frame
data_frame$y[3]
#> [1] "C"
```

This code will access the value at the third row and "y" column of the data_frame, and print it to the console. In this example, the value at the third row and "y" column of the data_frame is "C", so the code will print the value "C" to


```r
# Print the value at the first and second row of "y" column of the data frame
data_frame$y[c(1:2)]
#> [1] "A" "B"

# Print the value at the third row and "y" column of the data frame
data_frame$y[c(1:2)]
#> [1] "A" "B"
```

However in applied setting we use either `dplyr` package to manipulate data frame. So for now we will not use data frame until few weeks.

### List and extraction
The list() function in R is used to create a list, which is a data structure that allows you to store and manipulate "a collection of objects." A list can contain objects of different types, including other lists, and can be modified dynamically.

Here are two matrices, two data frames, and two vectors. We can use the list() function and specify the matrices, data frames, and vectors as arguments. Here is an example of how you could do this:


```r
# Define two matrices, each containing the values 1, 2, 3, 4, 5
matrix1 <- matrix(c(1, 2, 3, 4, 5, 6), nrow = 2, ncol = 3)
matrix2 <- matrix(c(5, 4, 3, 2, 1, 8), nrow = 2, ncol = 3)

# Define two data frames, each containing the values 1, 2, 3, 4, 5
data_frame1 <- data.frame(x = c(1, 2, 3, 4, 5), y = c(-1,-4, -9,-8,-7))
data_frame2 <- data.frame(win = c(5, 4, 3, 2, 1), loss = c(-2,-90,-3,-2,-0.5))

# Define two vector
numeric_vector <- c(1:100)
character_vector <- c("alpha", "beta", "gamma", "delta", "theta")

# Create a list that contains the two matrices and the two data frames
my_list <- list(matrix1, matrix2, data_frame1, data_frame2, numeric_vector, character_vector)
```

Finally, lets print the my_list variable to the console, and the output will look like this:


```r
# Print the list
my_list
#> [[1]]
#>      [,1] [,2] [,3]
#> [1,]    1    3    5
#> [2,]    2    4    6
#> 
#> [[2]]
#>      [,1] [,2] [,3]
#> [1,]    5    3    1
#> [2,]    4    2    8
#> 
#> [[3]]
#>   x  y
#> 1 1 -1
#> 2 2 -4
#> 3 3 -9
#> 4 4 -8
#> 5 5 -7
#> 
#> [[4]]
#>   win  loss
#> 1   5  -2.0
#> 2   4 -90.0
#> 3   3  -3.0
#> 4   2  -2.0
#> 5   1  -0.5
#> 
#> [[5]]
#>   [1]   1   2   3   4   5   6   7   8   9  10  11  12  13
#>  [14]  14  15  16  17  18  19  20  21  22  23  24  25  26
#>  [27]  27  28  29  30  31  32  33  34  35  36  37  38  39
#>  [40]  40  41  42  43  44  45  46  47  48  49  50  51  52
#>  [53]  53  54  55  56  57  58  59  60  61  62  63  64  65
#>  [66]  66  67  68  69  70  71  72  73  74  75  76  77  78
#>  [79]  79  80  81  82  83  84  85  86  87  88  89  90  91
#>  [92]  92  93  94  95  96  97  98  99 100
#> 
#> [[6]]
#> [1] "alpha" "beta"  "gamma" "delta" "theta"
```

As you can see, the my_list variable contains a list with four elements, each of which is one of the matrices or data frames defined in the code. You can access or modify the elements in the list using the [[]] operator.

To use the [[]] operator to access or modify an element in a list, you can specify the position of the element in the list as the first argument, and the name of the element as the second argument. Here is an example of how you could do this:


```r
# Access the second matrix in the list
my_list[[2]]
#>      [,1] [,2] [,3]
#> [1,]    5    3    1
#> [2,]    4    2    8

# Access the first matrix in the list
my_list[[3]]
#>   x  y
#> 1 1 -1
#> 2 2 -4
#> 3 3 -9
#> 4 4 -8
#> 5 5 -7
```

Now we can also extract elements within those lists.


```r
# Access the second matrix in the list and extract the second row and third element
my_list[[2]][2,3]
#> [1] 8

# Access the second matrix in the list and get the wins
my_list[[4]]$win
#> [1] 5 4 3 2 1

# Access the second matrix in the list and get the wins, with 1, 4 element
my_list[[4]]$win[c(1,4)]
#> [1] 5 2
```

We can also give names to the list as following.


```r
# Lets define my_list2 which is same as my_list
my_list2 <- my_list

# Also give some names in my_list2. Note that we have 6 objects within list, so there must be 6 names.
names(my_list2) <- c("matrix1", "matrix2", "dataframe1", "dataframe2", "vector1", "vector2")
```

With these name its even easier to extract with `$`.


```r
# Access the second matrix in the list
my_list2$matrix2
#>      [,1] [,2] [,3]
#> [1,]    5    3    1
#> [2,]    4    2    8

# Access the first matrix in the list
my_list2$dataframe1
#>   x  y
#> 1 1 -1
#> 2 2 -4
#> 3 3 -9
#> 4 4 -8
#> 5 5 -7

# Access the second matrix in the list and extract the second row and third element
my_list2$matrix2[2,3]
#> [1] 8

# Access the second matrix in the list and get the wins
my_list2$dataframe2$win
#> [1] 5 4 3 2 1

# Access the second matrix in the list and get the wins, with 1, 4 element
my_list2$dataframe2$win[c(1,4)]
#> [1] 5 2
```


## Summary
In R, vectors, matrices, data frames, and lists are commonly used data structures that allow you to store and manipulate collections of objects.

A vector is a one-dimensional array that can contain objects of the same type, such as numbers or character strings. Vectors are often used to represent a single variable or a set of observations and are typically used in mathematical operations and statistical functions.

A matrix is a two-dimensional array that can contain objects of the same type, such as numbers or character strings. Matrices are often used to represent data in a tabular format and are typically used in linear algebra and statistical modeling.

A data frame is a two-dimensional array that can contain objects of different types, such as numbers, character strings, and logical values. Data frames are often used to represent data in a tabular format and are typically used in data analysis and statistical modeling.

A list is a data structure that allows you to store and manipulate a collection of objects, including other lists. Lists are often used to represent complex data structures and are typically used in data manipulation and programming.

In summary, vectors, matrices, data frames, and lists are essential data structures in R and are frequently used in data analysis and statistical modeling.

## Some additional resources
Check this YouTube playlist of R tutorial - Learn R Programming from data camp (https://www.youtube.com/playlist?list=PLjgj6kdf_snYBkIsWQYcYtUZiDpam7ygg), or if you still prefer to read check this free book Hands-On Programming with R by Garrett Grolemund chapter 2 "The Very Basics" (https://rstudio-education.github.io/hopr/basics.html).
