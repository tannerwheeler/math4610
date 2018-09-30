# Secant Method

**Routine Name:**           secantMethod

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This routine will run the secant method.  Given two points it will use the secant line and the slope of that line to get closer to the root.

**Input:** This method has five parameters.  First and Second, `x0` and `x1`.  These are the two points used to compute the secant line.  Third, `f` is the function you are finding the root for.  This will need to be created as another method, but the name of the method can be passed as a parameter without parenthesis as shown in Usage/Example.  Fourth, `tol` is the tolerance you want or to what accuracy do you want to find the root. Fifth, `maxiter` the maximum number of iterations you want the method to compute.

**Output:** This routine returns a decimal number of the root for the function.

**Usage/Example:**
First you must create the method for `f`:
```
def function(x):
    return x**2 -3
```
Now you can call the secant method with `a = -3`, `b = 0`, `tol = 0.00000001`, and `maxiter = 20`:
```
secantMethod(-3, 0, function, 0.00000001, 20)
```
This will return:
```
-1.7320508075688774
```

**Implementation/Code:** The following is the code for secantMethod(x0, x1, f, tol, maxiter)
```
def secantMethod(x0, x1, f, tol, maxiter):
    iter = 0
    error = 10
    
    while error > tol and iter < maxiter:
        iter = iter + 1
        
        x2 = x1 - (f(x1) * ((x1 - x0)/(f(x1) - f(x0))))
        
        error = abs(x2 - x1)
        
        x0 = x1
        x1 = x2
    
    return x1
```

**Last Modified:** September/2018
