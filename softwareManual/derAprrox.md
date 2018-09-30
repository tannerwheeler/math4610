# Derivative Approximation

**Routine Name:**           dxApprox

**Author:** Tanner Wheeler

**Language:**  Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This will give a derivative approximation.  The smaller the value for `h` the better the approximation will be.

**Input:** There are two inputs for this method.  First, `x` the value of x where you would like to compute the derivative value.  Second, `h` the smaller this value is the closer it gets to an exact approximation.  If `h` is too small however machine precision might interpret the value as 0 and try to divide by 0.  You will need to create another method with the desired function called `functionToRun(x)`.

**Output:** This routine returns a decimal number of the derivative approximation.  The derivative represents the slope of the given function at the given x value.

**Usage/Example:**

If I wanted to compute the derivative of `x^2 - 3` at `x = 3` with my `h = 0.000000001`.  I would use the method set up:
```
dxApprox(3, 0.000000001)
```
This would then return the slope of `x^2 -3` at `x = 3` is:
```
6.000000496442226
```

**Implementation/Code:** The following is the code for dxApprox(x, h)
```
def dxApprox(x, h):
    return (functionToRun(x + h) - functionToRun(x)) / h
```

**Last Modified:** September/2018
