# Absolute Error

**Routine Name:**           errorAbs(x, y)

**Author:** Tanner Wheeer

**Language:** Python.  This code can be run on a python 3 compiler.  The file can be imported and then the method will run.

**Description/Purpose:** This routine will compute the absolute error between the computed answer and the exact answer.

**Input:** There are two inputs needed.  `x` the exact solution and `y` the computed solution.

**Output:** This routine returns a decimal number representing the absolute error of the solution.

**Usage/Example:**
To run this method.  You will need to call the method inserting the two parameters.  If `x = 1` and `y = 1.75` you would call it as:
```
errorAbs(1, 1.75)
```
This would return or output (depending on how you use it):
```
0.75
```

**Implementation/Code:** The following is the code for `errorAbs(x,y)`
```
def errorAbs(x, y):
    return abs(x - y)
```

**Last Modified:** September/2018
