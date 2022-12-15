# Index universal life insurance

## Case study, index universal life insurance
> Case-1: An insurance sales agent wants to sell me an index universal life insurance. The idea is pretty simple. They will invest my premium in the S&P 500 Index Stock Market. If the market yields a negative return, the agent says, I will incur no loss. If snp_ret < 0, my returns will be zero. Sweet Deal! However, if the market grew more than 13%, I would be capped at 13%. If the market ranges between 0 to 13%, my return will be the same as the market return. The policy is for 30 year period.

* Question-1. Intuitively, is it a good idea? Explain why or why not?

* Question-2. Select the first 30 elements from `snp_ret` because the policy is for 30 years. Develop if-else conditional statement.



```r
r <- sample(x = ..., size = length(snp_ret[1:30]), replace = F)
for(i in 1:length(...)){
  if(r[...]<=0){
    r[...] = 0
  }
  if(r[...]>=...){
    r[...] = 0.13
  }
  else
  {
    r[...] = r[..]
  }
  
```

* Question-3. Find the value of the portfolio of your recursive investing.

* Question-4. Model the sequence risk. What is the 95% confidence interval of the cumulative portfolio value?

