# Newton's Method

**Routine Name:**           newtonMethod

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This routine will run Newton's Method.  Given one points it will use the slope at that point to find another point closer to the root and use that slope to again move closer.  This process is repeated until the computed root is less than the tolerance given.  This can't be used if the derivative at the point `x` equals zero. 

**Input:** This method has five parameters.  First, `x0`.  This is the starting point.  Second and Third, `f` and `fd` is the function you are finding the root for and the derivative of that function.  These will need to be created as another method, but the name of the method can be passed as a parameter without parenthesis as shown in Usage/Example.  Fourth, `tol` is the tolerance you want or to what accuracy do you want to find the root. Fifth, `maxiter` the maximum number of iterations you want the method to compute.

**Output:** This routine returns a decimal number of the root for the function.

**Usage/Example:**
First you must create the method for `f` and `fct`:
```
def function(x):
    return x**2 -3
    
def functionDerivative(x):
    return 2 * x
```
Now you can call the bisection method with `x0 = -3`, `tol = 0.00000001`, and `maxiter = 20`:
```
newtonMethod(-3, function, functionDerivative, 0.00000001, 20)
```
This will return:
```
-1.7321166822956011
```

**Implementation/Code:** The following is the code for newtonMethod(x0, f, fd, tol, maxiter)
```
def newtonMethod(x0, f, fd, tol, maxiter):
    iter = 0
    error = 10
    
    while error > tol and iter < maxiter:
        iter = iter + 1
        
        #print(x0) testing purposes
        
        x1 = x0 - (f(x0)/fd(x0))
        
        error = abs(x1 - x0)
        
        x0 = x1
    
    return x0
```

**Last Modified:** September/2018
