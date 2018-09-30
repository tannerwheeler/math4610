## Homework #1
#### Tanner Wheeler

### 1. Problem: Write routines that can be used to compute the absolute error and relative error.

#### Answer:


### 2. Problem: Write code that implements the derivative approximation for various values of the paramter `h`. Use the routine you create, along with the code for the relative and absolute error, to investigate this approximation as `h` tends to zero. Graph the results starting with `h = 1` and then dividing `h` by two until the approximation fails to get better. Hint: Use any function you want from calculus. In fact, it would be best to try a couple of different functions. Add a summary of your work in your software manual as an example of the importance of absolute and relative errors in machine precision computations

#### Answer:



### 3a. Problem: For `f(x)=√x` use the derivative approximation using to examine machine precision errors as `h` tends to zero. Then use the conjugate of the numerator to rewrite the derivative formula.

#### Answer:



### 3b. Problem: In this problem, approximate the derivative of `f(x)=sin(x)` at `x_0=0`. 

#### Answer:



### 4. Problem: For this problem, you will need to write a routine (or possibly more than one routine) that searches for a root of a given function using function iteration.

#### Answer:


### 5. Problem: Implement the Bisection Method and test the method on the functions in the previous problem. Also, include an entry in your software manual with the results from the tests on the given function.

#### Answer:


### 6. Problem: Repeat the previous exercise with code written to implement Newton's method.

#### Answer:


### 7. Problem: Repeat the previous exercise with code written to implement the secant method approximation of Newton's method.

#### Answer:


### 8. Problem: Repeat the previous exercise with code written to implement a hybrid method using bisection to guarantee the roots are bracketed and Newton's method for faster convergence once the interval has been narrowed. Make sure that the bisection method reduces the interval size by one order of magnitude `(10^−1)` when the method is necessary. Then try one step of Newton's method to see if the interval has been reduced enough.

#### Answer:



### 9. Problem: Repeat the previous exercise with code written to implement a hybrid method using bisection to guarantee the roots are bracketed and the secant method for faster convergence once the interval has been narrowed. Make sure that the bisection method reduces the interval size by one order of magnitude `(10^−1)` when the method is necessary. Then try one step of the secant method to see if the interval has been reduced enough.

#### Answer:


## 10. Problem: Perform an online search for references to bracketing of roots of functions of a single real variable. Look for applications an explanations of how to bracket roots of nonlinear functions. Make sure that you cite at least three sources. You can cite web sites and/or web pages that discuss bracketing.

#### Answer:
