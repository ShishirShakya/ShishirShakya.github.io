# Gradient descent 

## Intution
Gradient descent is an iterative optimization algorithm used to find a function's "minimum" value by taking small steps in the direction opposite to the gradient (slope) of the function at the current position. 

Let me give an intuitive example. 

1. Given a function, first, analytically find the gradient. For example, given the function $y = f(x) = 2x^2 - 8x + 3$, the gradient is $f'(x) = 4x - 8$.

2. Calculate the gradient of the function at the initial guess. Guess can be any number. It does not matter. Usually, we start at zero. So let's evaluate the gradient at 0. $f'(x_0 = 0) = 4x - 8 = 4(0) - 8 = -8$.

3. We want to learn from this gradient. How much we want to learn is defined by the learning rate parameter. For our example, let's define the learning parameter as $\alpha = 0.01$. Then we learn say $\alpha f'(x_0 = 0)$ = $0.01 (-8) = -0.08$.

4. Now, we update the value of the initial guess of 0 with what we learn. Thus new guess say, $x_1$, is $x_1 = x_0 - \alpha f'(x_0 = 0)$. In our example, $x_1 = 0-(-0.08) = 0.08$. Note if the gradient is decreasing, you would do the opposite-- increase the value of x. And if the gradient is positive or increasing, you would do the opposite-- decrease the value of x.

5. Next, we calculate the function's gradient using $x_1$ such that $f'(x_0 = 0) = 4(0.08) - 8 = -7.68$. Then again update the value $x_1$ to $x_2$ as $x_2 = x_1 - \alpha f'(x_1 = 0.01)$ or $x_2 = 0.08 - 0.01(-7.68) = 0.157$. 

6. We iterate this process for a long time, say 1000 times, which enables us to find the value of $x$ that minimizes the function $y = f(x) = 2x^2 - 8x + 3$.

## Gradient descent using "for loop" in R codes
Let's first define the function and gradient of the function.


```r
# Define the function
f = function(x) {
  return(2*x^2 - 8*x + 3)
}

# Define the gradient of the function
f_grad = function(x) {
  return(4*x - 8)
}
```

Now, we define three criteria. First is the initialization value. We choose $x = 0$. Second is the learning rate. We choose 0.01. Third is the how many time we want to iterate it, say 1000 times. 


```r
# Set the initial value of x
x = 0

# Set the learning rate
alpha = 0.01

# Set the number of iterations
n_iter = 1000
```

Now, with this information, let's implement gradient descent. I am suppressing the results of this table because it will print 1000 rows of x values. There is a better way to do it. I will show that latter. When you use this code, simply un-comment `print(x)`.


```r
# Perform gradient descent
for (i in 1:n_iter) {
  x = x - alpha * f_grad(x)
  #print(x)
}
```

After running this algorithm, just simply check the value of x, you will find the answer of x.


```r
# Print the final value of x
print(x)
#> [1] 2
```

## Gradient descent using "while" in R codes

Lets use the while conditional statement to implement the loop. We have similar set up. 

```r
# Define the function
f = function(x) {
  return(2*x^2 - 8*x + 3)
}

# Define the gradient of the function
f_grad = function(x) {
  return(4*x - 8)
}

# Set the initial value of x
x = 0

# Set the learning rate
alpha = 0.1

# Set the maximum number of iterations
max_iter = 1000
```

However, here we want to initialize the iteration from 0. We also want to set some tolerance of error, say 0.1. This means we are okay to have a gradient near 0.1 rather than perfectly zero.


```r
# Set the tolerance
tol = 0.1

# Initialize the number of iterations
n_iter = 0
```

Next, we use the while statement. In R, a while statement is used to execute a block of code repeatedly as long as a specified condition is true. The condition is an expression that is evaluated before each iteration of the loop. If the condition evaluates to TRUE, the code within the loop is executed. If the condition evaluates to FALSE, the loop is terminated, and control is passed to the next statement after the loop.

In our case, while the n_iter < max_iter, calculate the gradient of the function. If the absolute value of the gradient of the function is less than our tolerance of error, in our case 0.1, stop or break the for a loop.



```r
# Perform gradient descent
while (n_iter < max_iter) {
  # Calculate the gradient of the function
  grad = f_grad(x)
  
  # Check if the gradient is below the tolerance
  if (abs(grad) < tol) {
    #print("converged!")
    break
  }
  
  # Update the value of x
  x = x - alpha * grad
  
  # Increment the number of iterations
  n_iter = n_iter + 1
  
  print(paste0(n_iter," ", x))
}
#> [1] "1 0.8"
#> [1] "2 1.28"
#> [1] "3 1.568"
#> [1] "4 1.7408"
#> [1] "5 1.84448"
#> [1] "6 1.906688"
#> [1] "7 1.9440128"
#> [1] "8 1.96640768"
#> [1] "9 1.979844608"

# Print the final value of x
#print(x)
```


## Exercise
> I want you to play with a few of these parameters, change the initial value to 5 or -1, and see if you can get the results. Next, change the learning rate from 0.01 to 0.1 or 0.001. Examine if you converge to find the answer. Try changing the number of iterations as well. Explain your understanding.

> How would you determine if you got the correct solution or not? For example, can you adjust the above code to exhibit a prompt that "The solution doesnot converge, please adjust either intialization or learning rate or iteration."

