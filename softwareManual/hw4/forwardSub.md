# Forward Substitution

**Routine Name:** fowardSub

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This will perform forward substitution given a matrix and a vector.  It solves the equation `Ax = b` where `A` is a lower triangular matrix of dimensions mxn and `b` is a vector of length n.

**Input:** The first input needs to be a two dimensional array of dimensions mxn.  The second input needs to be an array of length n.  The dimensions need to be checked before calling the method.

**Output:** This method will return the solution `x` to the equation `Ax = b`.  This will be returned as an array of length n.

**Usage/Example:**
First let's define `c` and `d`
```
c = [[0.0] * 3 for k in range(0, 3)]
c[0][0] = 7.0
c[1][0] = 3.0
c[1][1] = 10.0
c[2][0] = 1.0
c[2][1] = 2.0
c[2][2] = 15.0

d = [0.0 for i in range(0, 3)]
d[0] = 2
d[1] = 3
d[2] = 2
```
Now we have
```
c = [[7.0, 0.0, 0.0],
     [3.0, 10.0, 0.0],
     [1.0, 2.0, 15.0]]

d = [2, 3, 2]
```
Now let's print to the console the solution to our method
```
print(forwardSub(c, d))
```
This prints
```
[0.2857142857142857, 0.21428571428571427, 0.08571428571428572]
```


**Implementation/Code:** The following is the code for forwardSub(a, b)
```
def forwardSub(a,b):
    n = len(b)
    x = [0.0 for i in range(0,n)]
    
    x[0] = b[0]/a[0][0]
    
    for i in range(1,n):
        sumVal = 0.0
        for j in range(0, i):
            sumVal = sumVal + a[i][j]*x[j]
        
        x[i] = (b[i] - sumVal)/a[i][i]
    
    return x
```

**Last Modified:** December 2018

