# Recursive investment

## Recursive investment

Imagine that you intend to do recursive investing. This means you plan to invest every year. In the table below, I show you the value of your portfolio. For example, in column (8), the cumulative value of your portfolio in the fifth year is 6.129.

r | R = (1+r) | t | Year1 | Year2 | Year3 | Year4| Cumulative |
:-:  | :-:  |:-:  | -: | -:  | -:  |-:  |-: |
(1) | (2) | (3) | (4) | (5) | (6) | (7)| (8) |
$-0.05$ | $0.95$ | $1$ | $0.95$ | $0$ | $0$ | $0$ | $0.95$ |
$0.1$ | $1.1$ | $2$ | $0.95 \times 1.1 = 1.045$ | $1.1$ | $0$ | $0$ | $2.145$ |
$0.2$ | $1.2$ | $3$ | $0.95 \times 1.1 \times 1.2 = 1.254$ | $1.1 \times 1.2 = 1.32$ | $1.1$ | $0$ | $3.674$ |
$0.3$ | $1.3$ | $4$ | $0.95 \times 1.1 \times 1.2 \times 1.3 = 1.643$ | $1.1 \times 1.2 \times 1.3 = 1.716$ | $1.2 \times 1.3 = 1.56$ | $1.3$ | $6.219$ |

Let me explain this table to you. Let's first focus on column (4). So you invested 1 dollar, and the first year, you lost 5%. Thus your portfolio is only 1(1-0.05) = 0.95. However, second year your growth was 10%, thus your 0.95 dollar grew by 10% or 0.95(1+0.1) = 0.95(1.1) =1.045. In the third year, your growth was 20%. Hence your 1.045 dollars grew as 1.045(1.2)=1.32, then 1.32 dollars grew by 30% as 1.32(1.3) = 1.716. Hence the first dollar you invested grew to 1.716 dollars, a solid 71.6% return.

However, you were wise to do recursive investing. See column (5). So in the second year, you made an additional 1 dollar investment, which grew 10% to 1.1 dollars. That 1.1 dollars grew 20% in the third year to become 1.1(1.2)=1.32 dollars, which in the fourth year became 1.32(1.3)=1.56. Hence 1 dollar you invested in the second year became 1.56 dollars, another solid 56% growth.

Now you work your logic through column (6) and column (7).

So overall, you invested 4 dollars, which became 6.219 dollars at the end of the fourth year.

Let's code this in R.

```r
# Let call the growth rate as r
r <- c(-0.05, 0.1,0.2,0.3)
# Lets define the 1+r 
R <- 1+r

# Initialize a vector
fifth_year_return <- c()

# Perform a for loop
for(i in 1:length(R)){
    growth <- cumprod(R[i:length(R)])
  
    fifth_year_return[i] <- growth[length(growth)]
}
fifth_year_return
#> [1] 1.6302 1.7160 1.5600 1.3000
sum(fifth_year_return)
#> [1] 6.2062
```
 
This code calculates the cumulative product of the elements in the R vector. It does this by creating an empty vector called fifth_year_return and then using a for loop to iterate over the elements of the R vector.

For each iteration of the loop, the code calculates the cumulative product of the elements in the R vector using the cumprod() function. This function calculates the cumulative product of the elements in a vector, which is the product of all of the elements in the vector up to a given point.

The code then stores the result of the cumprod() function in a temporary vector called growth. This vector contains the cumulative product of the elements in the R vector up to the current iteration of the loop.

Next, the code stores the last element of the growth vector in the fifth_year_return vector. This means that the fifth_year_return vector will contain the cumulative product of the elements in the R vector for each element in the R vector.

Once the for loop has finished executing, the code prints the fifth_year_return vector to the console and then calculates the sum of the elements in the vector using the sum() function. This gives the total cumulative product of the elements in the R vector.

Let's examine the code more detailedly. `length()` function. The length() function is a built-in function in the R programming language. It is used to determine the length of an object, such as a vector or a list. `length(R)` prompts 4 which means the vector has 4 elements.

`R[]` helps to extract the elements. For example, `R[1]` will extract the first element which is 0.95. We can extract multiple elements as well. `R[1:3]` will extract first three elements 0.95, 1.1, and 1.2. Thus `R[i:length(R)]` will extract multiple elements where `i' runs from 1 to the length of R. Hence `R[1:5]` will give the first four elements of vector R, `R[2:5]` gives the second element to the fourth element.

Then we can implement `cumprod()` function to run a cumulative product function. Note that `cumprod()` generates a vector, which we store in object called `growth`. We are only interested in the last element of the growth vector. Then we save this in `fifth_year_return` vector. Finally we sum all the elements of `fifth_year_return` vector.

> Case-1: You decided to do recursive investing. Your friends say that he can deliver a growth rate of 10%, 20%, and 30%, but in one year, there will be a 5% loss. But he is not so sure of the sequences of returns. Since he is not so sure about the sequence of returns, you can simulate the sequences of returns with random sampling. Perform 1000 random draws and record the probable values of your portfolio. What is the 95% confidence interval of the cumulative portfolio value?


```r
portfolio_value <- c()
for(....){
  r <- c(0.3, 0.1, 0.2, -0.05)
  sample_r <- sample(x = ..., size = ..., replace = FALSE)
  R <- ....

  portfolio <- c()
  for(...){
    portfolio[i] <- cumprod(...)[...]
  }
  portfolio_value[j] <- sum(...)
}
hist(portfolio_value)
```



> Case-2: In the following R codes, I provide Historical S&P 500 Index Stock Market Returns (https://www.thebalancemoney.com/stock-market-returns-by-year-2388543) from 1980 onwards. What is the expected growth of your recursive investment? Let's imagine you only invested $1 religiously every year.


```r
snp_ret <- c(
  0.185,
  0.052,
  0.168,
  0.315,
  -0.031,
  0.305,
  0.076,
  0.101,
  0.011,
  0.372,
  0.227,
  0.330,
  0.2858,
  0.2104,
  -0.091,
  -0.1189,
  -0.221,
  0.2868,
  0.1088,
  0.0491,
  0.1579,
  0.0549,
  -0.370,
  0.2646,
  0.1506,
  0.0211,
  0.160,
  0.3239,
  0.1369,
  0.0138,
  0.1196,
  0.2183,
  -0.0438,
  0.3149
)
```


> Case-3: What the past 35 years looked like might look different in the future. You decided to remain invested for the next 35 years. You need to find out the future sequences of growth or risk. You can randomize the historical sequences, as these returns could occur in any random order. Simulate in 1000 trials R. With your simulation, should a rational investor invest in the US stock market? What is the 95% confidence interval of the cumulative portfolio value at the end of 35 years?
