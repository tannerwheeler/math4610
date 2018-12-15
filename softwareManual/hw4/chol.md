# Cholesky Factorization

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** chol

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This will perform cholesky factorization on a matrix.  The matrix will be changed to a symmetric matrix that is upper triangular with its transpose in the lower triangular half.  This will only work if the matrix is symmetric.

**Input:** The only input is a two dimensional array of numbers with dimensions nxn.  The dimensions will need to be checked before calling the method.

**Output:** There is nothing returned from this method.  Python passes parameters by reference so the input array will be modified after the function call.

**Usage/Example:**
First define `c` as a 5x5 matrix
```
c = [[0.0] * 5 for k in range(0,5)]
c[0][0] = 7.0
c[0][1] = 3.0
c[0][2] = 1.0
c[1][0] = 3.0
c[1][1] = 10.0
c[1][2] = 2.0
c[2][0] = 1.0
c[2][1] = 2.0
c[2][2] = 15.0
c[3][3] = 10.0
c[4][4] = 12.0
```
Now we have
```
c = [[7.0, 3.0, 1.0, 0.0, 0.0],
     [3.0, 10.0, 2.0, 0.0, 0.0],
     [1.0, 2.0, 15.0, 0.0, 0.0],
     [0.0, 0.0, 0.0, 10.0, 0.0],
     [0.0, 0.0, 0.0, 0.0, 12.0]]
```
Now call the method using our matrix array
```
chol(c)
```
This changes `c` to
```
c = [[2.6457513110645907, 1.1338934190276817, 0.3779644730092272, 0.0, 0.0],
     [1.1338934190276817, 2.951996902824546, 0.53232731034541, 0.0, 0.0],
     [0.3779644730092272, 0.53232731034541, 3.817560803943177, 0.0, 0.0],
     [0.0, 0.0, 0.0, 3.1622776601683795, 0.0],
     [0.0, 0.0, 0.0, 0.0, 3.4641016151377544]]
```


**Implementation/Code:** The following is the code for chol(a)
```
def chol(a):
    n = len(a)
    
    for k in range(0, n-1):
        a[k][k] = math.sqrt(a[k][k])
        for i in range(k+1, n):
            a[i][k] = a[i][k]/a[k][k]
        for j in range(k+1, n):
            for i in range(j, n):
                a[i][j] = a[i][j] - a[i][k] * a[j][k]
                
    a[n-1][n-1] = math.sqrt(a[n-1][n-1])
    
    for i in range(0, n):
        for j in range(i+1, n):
            a[i][j] = a[j][i]
    
    return #Parameters are passed in by reference by default
            #parameter a has been modified with the lower part as the 
            #cholesky factorization and the upper part as the transpose
            #of the chalesky factorization.  Diagonal should be same for
            #both triangles.
```

**Last Modified:** December 2018

