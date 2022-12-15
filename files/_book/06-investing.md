# Investing basics

## An angel investor
An angel investor (a private investor, seed investor, or angel funder) is a high-net-worth individual who provides financial backing for small startups or entrepreneurs, typically in exchange for ownership equity in the company. Often, angel investors are found among an entrepreneur's family and friends.

Suppose you are an angel investor in one of your friends' business. Your friend said he would return 10% every year for the next five years. What is the expected growth of your investment? Let's imagine you only invested $1. Then, we know with the compound interest formula that your principal of 1 dollar will grow 10% every year for next five year i.e., 
\[A = P(1+r)^t\]
\[A = 1(1+0.1)^5 = 1.4641\]

This means that your initial investment of 1 dollar will be 1.4641 dollars. Let me show you how to do this in R.


```r
# Let call the growth rate as r
r <- c(0.1, 0.1, 0.1, 0.1)

# Lets define the 1+r 
R <- 1+r

# You can simply do cumulative product as
portfolio <- cumprod(R)

# print
print(portfolio)
#> [1] 1.1000 1.2100 1.3310 1.4641

# To find the last year's total return
fifth_year_return <- portfolio[length(portfolio)]

print(fifth_year_return)
#> [1] 1.4641
```

## Exercise
> Case-1: You got another friend with a brilliant idea. However, your friends say that for the first year, you will likely incur a loss of 5%, then you will gain 10%, 20%, 30%, and 40%. How will your $1 initial investment would grow? Is this a better opportunity than your previous friend's project?

> Case-2: In the following R codes, I provide Historical S&P 500 Index Stock Market Returns (https://www.thebalancemoney.com/stock-market-returns-by-year-2388543) from 1980 onwards. What is the expected growth of your investment? Let's imagine you only invested $1.


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

> Case-3: One of my students has correctly identified that an investor should adjust for inflation, as investors are more interested in the real dollar value than the nominal value. I have gathered the inflation of the past 34 years since 1980. We can define the real return as the difference between a nominal return to inflation. What is the inflation-adjusted value of the portfolio?


```r
inflation <- c(0.189805,
               0.0366456,
               0.040777411,
               0.04827003,
               0.053979564,
               0.04234964,
               0.030288197,
               0.02951657,
               0.026074416,
               0.028054197,
               0.029312042,
               0.023376899,
               0.015522791,
               0.021880272,
               0.033768573,
               0.028261711,
               0.015860316,
               0.02270095,
               0.026772367,
               0.033927468,
               0.032259441,
               0.028526725,
               0.038391003,
               -0.003555463,
               0.016400434,
               0.031568416,
               0.020693373,
               0.014648327,
               0.01622223,
               0.001186271,
               0.012615832,
               0.0213011,
               0.024425833,
               0.018122101)

real_return <- snp_ret - inflation
```


