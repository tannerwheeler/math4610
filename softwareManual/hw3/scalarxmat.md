#  Scalar Multiplication into a Matrix

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** scalarmultimatrix

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This will mutltiply a scalar into a given matrix.

**Input:** This method takes one two dimensional array as its first input and one float point number as its second input.

**Output:** This method will return a new two dimensional array that is a scalar multiple of the input array.

**Usage/Example:** 
First let's create a matrix `a` whose dimensions are 3x2 and set its values.
```
n = 2
m = 3

a = [[float(0)] * n for i in range(0,m)]

a[0][0] = float(1)
a[0][1] = float(8)
a[1][0] = float(4)
a[1][1] = float(4)
a[2][0] = float(5)
a[2][1] = float(6)
```
Now we have 
```
a = [[1.0, 8.0], 
     [4.0, 4.0], 
     [5.0, 6.0]]
```
Let's create `c` as the scalar 3 multiplied into the matrix `a`.
```
c = scalar(a, 3)
```
Now we have
```
c = [[3.0, 24.0], 
     [12.0, 12.0],
     [15.0, 18.0]]
```


**Implementation/Code:** The following is the code for scalarmultimatrix(x, scalar)
```
def scalarmultimatrix(x, scalar):
    z = [[0] * len(x[1]) for k in range(0,len(x))]

    for i in range(0, len(x)):
        for j in range(0, len(x[i])):
            z[i][j] = x[i][j] * scalar
            
    return z
```

**Last Modified:** December 2018
