# L1 Matrix Norm

**Routine Name:** m1norm

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This method will compute the l_1 Matrix Norm given a specific matrix.

**Input:** This method has only one input.  This input `x` is a matrix of dimensions mxn.

**Output:** This method will return a double value representing the norm.

**Usage/Example:**
First create a matrix `a` with dimensions mxn and specify values for it.
```
n = 3
m = 3

a = [[float(0)] * n for i in range(0,m)]

a[0][0] = float(1)
a[0][1] = float(8)
a[0][2] = float(2)
a[1][0] = float(4)
a[1][1] = float(4)
a[1][2] = float(1)
a[2][0] = float(5)
a[2][1] = float(6)
a[2][2] = float(2)

a = [[1.0, 8.0, 2.0],
     [4.0, 4.0, 1.0],
     [5.0, 6.0, 2.0]]
```
Now let's print the output of our function given the matrix `a`.
```
print(m1norm(a))
```
This will print
```

18.0
```
to the console.


**Implementation/Code:** The following is the code for m1norm(x)
```
def m1norm(x):
    tempVal = 0.0
    newSum = 0.0
    
    for j in range(0, len(x[1])):
        for i in range(0, len(x)):
            tempVal = tempVal + abs(x[i][j])
        
        if tempVal > newSum:
            newSum = tempVal
            
        tempVal = 0.0
        
    return newSum
```

**Last Modified:** December 2018
