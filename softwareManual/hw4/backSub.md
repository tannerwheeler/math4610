# Back Substitution

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** backSub

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This will perform back substitution given a matrix and a vector.  It solves the equation `Ax = b` where `A` is an upper triangular matrix of dimensions mxn and `b` is a vector of length n.

**Input:** The first input needs to be a two dimensional array of dimensions mxn.  The second input needs to be an array of length n.  The dimensions need to be checked before calling the method.

**Output:** This method will return the solution `x` to the equation `Ax = b`.  This will be returned as an array of length n.

**Usage/Example:**
First let's define `c` and `d`
```
c = [[0.0] * 3 for k in range(0, 3)]
c[0][0] = 7.0
c[0][1] = 3.0
c[0][2] = 1.0
c[1][1] = 10.0
c[1][2] = 2.0
c[2][2] = 15.0

d = [0.0 for i in range(0, 3)]
d[0] = 2
d[1] = 3
d[2] = 2
```
Now we have
```
c = [[7.0, 3.0, 1.0], 
     [0.0, 10.0, 2.0],
     [0.0, 0.0, 15.0]]

d = [2, 3, 2]
```
Now let's print to the console the solution to our method
```
print(backSub(c, d))
```
This prints
```
[0.14952380952380956, 0.2733333333333333, 0.13333333333333333]
```


**Implementation/Code:** The following is the code for backSub(a, b)
```
def backSub(a,b):
    n = len(b)
    x = [0.0 for i in range(0,n)]
    i=n-1
    
    x[i] = b[i]/a[i][i]
    i=i-1
    
    while i >= 0:
        sumVal = 0.0
        for j in range(i+1, n):
            sumVal = sumVal + a[i][j]*x[j]
        
        x[i] = (b[i] - sumVal)/a[i][i]
        i=i-1    
    
    return x
```

**Last Modified:** December 2018
