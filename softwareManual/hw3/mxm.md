# Matrix Matrix Multiplication

**Routine Name:** mxm

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This method will perform matrix matrix multiplication on an mxn matrix and an nxp matrix.

**Input:** The two inputs should be two dimensional arrays.  The first should have the dimensions mxn and the second should have the dimensions nxp.

**Output:** The method will return a two dimensional array of dimensions mxp.  If the dimensions of the input matrices are incorrect then it will return an error message.

**Usage/Example:**
First let's define our two input arrays `a` and `b`.
```
n = 2
m = 3

a = [[float(0)] * n for i in range(0,m)]
b = [[float(0)] * m for i in range(0,n)]

a[0][0] = float(1)
a[0][1] = float(8)
a[1][0] = float(4)
a[1][1] = float(4)
a[2][0] = float(5)
a[2][1] = float(6)

b[0][0] = float(3)
b[0][1] = float(1)
b[0][2] = float(3)
b[1][0] = float(1)
b[1][1] = float(0)
```
Now we have 
```
a = [[1.0, 8.0],
     [4.0, 4.0],
     [5.0, 6.0]]
     
b = [[3.0, 1.0, 3.0],
     [1.0, 0.0, 2.0]]
```
Now let's create `c`
```
c = mxm(a, b)
```
We now have
```
c = [[11.0, 1.0, 19.0],
     [16.0, 4.0, 20.0],
     [0.0, 0.0, 0.0]]
```


**Implementation/Code:** The following is the code for mxm(m1, m2)
```
def mxm(m1, m2):
    if len(m1[1]) != len(m2):
        return "Error Invalid Sizes!"
    
    z = [[0.0] * len(m2[1]) for k in range(0,len(m1))]
    
    for i in range(0, len(m1[1])):
        for j in range(0, len(m1)):
            for k in range(0, len(m1[j])):
                z[i][j] = z[i][j] + (m1[i][k] * m2[k][j])
                
    return z
```

**Last Modified:** December 2018

