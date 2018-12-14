# LU Factorization

**Routine Name:** lufact

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This will change the math a into two parts.  It will have the lower half of the matrix the entries of `L` and the upper half of the matrix the entries of `U` with the diagonal entries are the diagonal entries of `U`.  If we were to multiply `L` and `U` together assuming the diagonal entries of `L` equal to 1.  Then `L*U = A`.

**Input:** This will be one two dimensional array of dimensions nxn.  The dimensions will need to be verified before calling the method.

**Output:** This method won't return anyhting but because python passes by reference the input variable has been modified.

**Usage/Example:**
First define `c`
```
c = [[0.0] * 3 for k in range(0, 3)]
c[0][0] = 7.0
c[0][1] = 3.0
c[0][2] = 1.0
c[1][0] = 3.0
c[1][1] = 10.0
c[1][2] = 2.0
c[2][0] = 1.0
c[2][1] = 2.0
c[2][2] = 15.0
```
Now we have 
```
c = [[7.0, 3.0, 1.0],
     [3.0, 10.0, 2.0],
     [1.0, 2.0, 15.0]]
```
Let's call our method
```
lufact(c)
```
Now we have
```
c = [[7.0, 3.0, 1.0],
     [0.42857142857142855, 8.714285714285715, 0.7142857142857144],
     [0.14285714285714285, 0.21311475409836064, 14.46135831381733]]
```

**Implementation/Code:** The following is the code for lufact
```
def lufact(a):
    n = len(a)
    for k in range(0, n-1):
        for i in range(k+1, n):
            lVal = a[i][k]/a[k][k]
            for j in range(k+1, n):
                a[i][j] = a[i][j] - lVal*a[i][k]
            a[i][k] = lVal
    return
```

**Last Modified:** December 2018

