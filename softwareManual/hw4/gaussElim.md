# Gaussian Elimination

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** gaussElim

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This will perform Gaussian Elimination on a matrix `A` and vector `b` for the equation `Ax = b`.  `A` doesn't have to be a square matrix.

**Input:** The first input should be a two dimensional array of dimensions mxn.  The second input should be an array of length n.  The dimensions need to be checked before calling the method.

**Output:** The method will return nothing.  Inputs in python are passed by reference.  This means the input arrays `a` and `b` will be modified after the method is run.

**Usage/Example:**
First define `a` and `b`.
```
a = [[0.0] * 3 for k in range(0, 2)]
a[0][0] = 7.0
a[0][1] = 3.0
a[0][2] = 1.0
a[1][0] = 3.0
a[1][1] = 10.0
a[1][2] = 2.0

b = [0.0 for i in range(0, 2)]
b[0] = 2
b[1] = 3
```
Now we have
```
a = [[7.0, 3.0, 1.0],
     [3.0, 10.0, 2.0]]

b = [2, 3]
```
Perform Gaussian Elimination
```
gaussElim(a, b)
```
Now we have
```
a = [[7.0, 3.0, 1.0],
     [0.0, 8.714285714285715, 1.5714285714285714]]

b = [2, 2.142857142857143]
```


**Implementation/Code:** The following is the code for gaussElim(a, b)
```
def gaussElim(a, b):
    
    for k in range(0, len(a)):
        for i in range(k+1, len(a)):
            factor = a[i][k]/a[k][k]
            
            for j in range(k, len(a[0])):
                a[i][j] = a[i][j] - factor * a[k][j]
   
            b[i] = b[i] - factor * b[k]
    
    return #In python all parameters are passed in by reference
           #Thus a and b have been changed.
```

**Last Modified:** December 2018

