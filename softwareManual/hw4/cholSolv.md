# Cholesky Factorization Solver

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** cholSolv

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This method will use Cholesky factorization to split a matrix `A` into a lower triangular part and an upper triangular part that are transposes of each other.  It will then perform forward substitution and back substitution to solve the equation `Ax = b`.  This method uses the methods[chol(a)](https://tannerwheeler.github.io/math4610/softwareManual/hw4/chol), [forwardSub(a,b)](https://tannerwheeler.github.io/math4610/softwareManual/hw4/forwardSub), and [backSub(a,b)](https://tannerwheeler.github.io/math4610/softwareManual/hw4/backSub).

**Input:** This method takes two inputs.  The first is a two dimensional array of dimensions mxn.  The second input should be an array of length n.

**Output:** This method will return the answer to the equation `Ax = b`.  This will be an array of length n.

**Usage/Example:**
First we need to define `c` and `d`
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

d = [0.0 for i in range(0, 5)]
d[0] = 11.0
d[1] = 15.0
d[2] = 18.0
d[3] = 10.0
d[4] = 12.0
```
Now we have
```
c = [[7.0, 3.0, 1.0, 0.0, 0.0], 
     [3.0, 10.0, 2.0, 0.0, 0.0],
     [1.0, 2.0, 15.0, 0.0, 0.0],
     [0.0, 0.0, 0.0, 10.0, 0.0],
     [0.0, 0.0, 0.0, 0.0, 12.0]]
     
d = [11.0, 15.0, 18.0, 10.0, 12.0]
```
Let's perform our method using `c` and `d` and print the output to the console.
```
print(cholSolv(c, d))
```
This will print
```
[0.9999999999999997, 1.0000000000000002, 1.0000000000000002, 0.9999999999999999, 1.0000000000000002]
```


**Implementation/Code:** The following is the code for cholSolv(a,b)
```
def cholSolv(a, b):
    chol(a)
    
    return backSub(a, forwardSub(a,b))
```

**Last Modified:** December 2018
