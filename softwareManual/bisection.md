# Bisection Method

**Routine Name:**           bisection

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This routine will run the bisection method.  Given two points it will look at a point between them and move one end point, depending on the result, to shrink the interval until it is at a root.

**Input:** This method has five parameters.  First and Second, `a` and `b`.  These are the two end points of the interval with `a < b`.  Third, `fct` is the function you are finding the root for.  This will need to be created as another method, but the name of the method can be passed as a parameter without parenthesis as shown in Usage/Example.  Fourth, `tol` is the tolerance you want or to what accuracy do you want to find the root. Fifth, `maxiter` the maximum number of iterations you want the method to compute.

**Output:** This routine returns a decimal number of the root for the function.  If `fct(a) * fct(b) > 0` then the method will return an error.

**Usage/Example:**
First you must create the method for `fct`:
```
def function(x):
    return x**2 -3
```
Now you can call the bisection method with `a = -3`, `b = 0`, `tol = 0.00000001`, and `maxiter = 20`:
```
bisection(-3, 0, function, 0.00000001, 20)
```
This will return:
```
-1.7320508075688772
```
If `a = -10` and `b = -3` then the method would return:
```
ERROR!
```

**Implementation/Code:** The following is the code for bisection(a, b, fct, tol, maxiter)
```
def bisection(a, b, fct, tol, maxiter):
    error = 10 * tol
    iter = 0
    
    fa = fct(a)
    fb = fct(b)
    
    if(fa * fb > 0):
            return "ERROR!"
    
    if(fa * fb == 0):
        if(fa == 0):
            return a;
        if(fb == 0):
            return b;
    
    while error > tol and iter < maxiter:
        
        iter = iter + 1
        
        c = (b + a) / 2
        fc = fct(c)
        
        if(fa * fc == 0):
            return c
        elif(fa * fc < 0):
            b = c
            fb = fc
        else:
            a = c
            fa = fc
            
        error = abs(b - a)
        
    return c
```

**Last Modified:** September/2018
