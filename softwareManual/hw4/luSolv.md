# LU Factorization Solver

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** luSolv

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This method will use LU factorization to split a matrix `A` into a lower triangular part and an upper triangular part.  It will then perform forward substitution and back substitution to solve the equation `Ax = b`.  This assumes the lower triangular part has 1's in the diagonal.

**Input:** This method takes two inputs.  The first is a two dimensional array of dimensions mxn.  The second input should be an array of length n.

**Output:** This method will return the answer to the equation `Ax = b`.  This will be an array of length n.

**Usage/Example:**
First we need to define `c` and `d`
```
c = [[0.0] * 3 for k in range(0, 3)]
c[0][0] = 7.0
c[1][0] = 3.0
c[1][1] = 10.0
c[2][0] = 1.0
c[2][1] = 2.0
c[2][2] = 15.0

d = [0.0 for i in range(0, 3)]
d[0] = 11.0
d[1] = 15.0
d[2] = 18.0
```
Now we have
```
c = [[7.0, 3.0, 1.0], 
     [3.0, 10.0, 2.0], 
     [1.0, 2.0, 15.0]]
     
d = [11.0, 15.0, 18.0]
```
Let's perform our method using `c` and `d` and print the output to the console.
```
print(luSolv(c, d))
```
This will print
```
[0.9595202381742504, 1.0996349638282334, 0.9844534412955467]
```


**Implementation/Code:** The following is the code for luSolv(a,b)
```
def luSolv(a,b):
    n = len(a)
    for k in range(0, n-1):
        for i in range(k+1, n):
            lVal = a[i][k]/a[k][k]
            for j in range(k+1, n):
                a[i][j] = a[i][j] - lVal*a[i][k]
            a[i][k] = lVal
    
    # Ly=b section using forward sub with diagonals equal to 1.
    y = [0.0 for i in range(0,n)]
    
    y[0] = b[0]
    
    for i in range(1,n):
        sumVal = 0.0
        for j in range(0, i):
            sumVal = sumVal + a[i][j]*y[j]


        y[i] = (b[i] - sumVal)
    
    # Ux=y section using back substitution.    
    x = [0.0 for i in range(0,n)]
    i=n-1
    
    x[i] = y[i]/a[i][i]
    i=i-1
    
    while i >= 0:
        sumVal = 0.0
        for j in range(i+1, n):
            sumVal = sumVal + a[i][j]*x[j]
        
        x[i] = (y[i] - sumVal)/a[i][i]
        i=i-1 

    return x
```

**Last Modified:** December 2018

