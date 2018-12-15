# Relative Error (L-Infinity Norm)

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** relVecInfError

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This will compute the relative error between two vectors using the l_infinity vector norm.  This can be run for any size of vector with integer, float, and double values.  This method does use the method [normInfvec(x, m)](https://tannerwheeler.github.io/math4610/softwareManual/hw3/linfnorm).

**Input:** There are three inputs for this method. The first vector is the approximation.  The second vector needs to be the exact solution you are comparing against.  The third input is the size of both vectors.  Both vectors need to be of the same size.

**Output:** This routine returns a double precision value for the absolute error using the l_infinity vector norm.

**Usage/Example:**
First let's create two vectors `c` and `d`, with `d` as our exact solution, of size 3 and set each element to a specific number.
```
m = 3

c = [float(0) for i in range(0, m)]
d = [float(0) for i in range(0, m)]

c[0] = 1.5
c[1] = 9.4
c[2] = 3.3

d[0] = 1
d[1] = 9
d[2] = 3
```
Now let's print out the value returned from our function given our vectors and their size.
```
print(relVecInfError(c, d, m))
```
This will print
```
0.05555555555555555
```
to the console.


**Implementation/Code:** The following is the code for relVecInfError(x, y, m)
```
def relVecInfError(x, y, m):
    z = [float(0) for i in range(0, m)]
    
    for i in range(m):
        z[i] = x[i] - y[i]
    
    return normInfvec(z, m) / normInfvec(y, m)
```

**Last Modified:** December 2018
