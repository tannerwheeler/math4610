# Absolute Error (L2 Norm)

**Routine Name:** absVec2Error

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This will compute the absolute error between two vectors using the l_2 vector norm.  This can be run for any size of vector with integer, float, and double values.  This method does use the method [norm2vec(x)](https://tannerwheeler.github.io/math4610/softwareManual/hw3/l2norm).

**Input:** There are three inputs for this method. The first two inputs are the two vectors you want to compare.  The third input is the size of both vectors.  Both vectors need to be of the same size the same size.

**Output:** This routine returns a double precision value for the absolute error using the l_2 vector norm.

**Usage/Example:**
First let's create two vectors `c` and `d` of size 3 and set each element to a specific number.
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
print(absVec2Error(c, d, m))
```
This will print
```
0.7071067811865476
```
to the console.


**Implementation/Code:** The following is the code for absVec2Error(x, y, m)
```
def absVec2Error(x, y, m):
    z = [float(0) for i in range(0, m)]
    
    for i in range(m):
        z[i] = x[i] - y[i]
    
    return norm2vec(z)
```

**Last Modified:** December 2018
