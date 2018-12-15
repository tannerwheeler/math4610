# Cross Product of a 3x3 Vector

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** crossprod

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This method will take the cross product of two vectors of length 3.  It will perform `x`x`y`.

**Input:** The inputs for this method need to be two vectors of length 3.  The first input will be `x` and the second will be `y`.

**Output:** This will return the cross product vector of the two vectors.

**Usage/Example:**
First let's create two vectors `c` and `d` of size 3 and set each element to a specific number.
```
c = [float(0) for i in range(0, 3)]
d = [float(0) for i in range(0, 3)]

c[0] = 1.5
c[1] = 9.4
c[2] = 3.3

d[0] = 1
d[1] = 9
d[2] = 3
```
Now let's print out the value return from our function given our created vectors.
```
print(crossprod(c, d))
```
This will print
```
[-1.4999999999999964, -1.2000000000000002, 4.1]
```
to the console.  Doing
```
crossprod(d,c)
```
will give
```
[1.4999999999999964, 1.2000000000000002, -4.1]
```

**Implementation/Code:** The following is the code for crossprod(x, y)
```
def crossprod(x,y):
    if len(x) != 3 and len(x) != 3:
        return "Error Vector is not in R3."
    
    newVector = [0 for i in range(0, len(x))]
    
    newVector[0] = (x[1]*y[2]) - (x[2]*y[1])
    newVector[1] = (x[2]*y[0]) - (x[0]*y[2])
    newVector[2] = (x[0]*y[1]) - (x[1]*y[0])
    
    return newVector
```

**Last Modified:** December 2018
