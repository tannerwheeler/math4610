# Gaussian Elimination Solver

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** gaussSolv

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This will solve the equation `Ax = b` where `A` is of dimensions mxn and `b` is a vector of length n.  The method uses the methods [gaussElim(a,b)](https://tannerwheeler.github.io/math4610/softwareManual/hw4/gaussElim) and [backSub(a,b)](https://tannerwheeler.github.io/math4610/softwareManual/hw4/backSub).

**Input:** The first input will need to be a two dimensional array of dimensions mxn.  The second input will need to be an array of length n.  The dimensions of the inputs need to be checked before calling the method.

**Output:** This method will return the solution `x` to the equation `Ax = b`.  This will be an array of length n.

**Usage/Example:**
First define `c` and `d`
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
Now let's print to the console the solution to our method
```
print(gaussSolv(c, d))
```
This prints
```
[1.0000000000000002, 0.9999999999999998, 0.9999999999999999]
```


**Implementation/Code:** The following is the code for gaussSolv(a, b)
```
def gaussSolv(a,b):
    gaussElim(a,b)
    
    return backSub(a,b)
```

**Last Modified:** December 2018

