# Matrix Vector Multiplication

**Routine Name:** mxv

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This method will perfom matrix vector multiplication.

**Input:** This will take a two dimensional array as the first input with dimensions mxn.  The second input will be an array of length n. 

**Output:** This will return an array of length n.  If the array isn't the correct length the method will return an error message.

**Usage/Example:** 
First let's create a matrix `a` whose dimensions are 3x2 and `e` whose length is 2 with only 1's as its values.  Now set `a`'s values.
```
n = 2
m = 3

a = [[float(0)] * n for i in range(0,m)]
e = [float(1) for i in range(0, n)]

a[0][0] = float(1)
a[0][1] = float(8)
a[1][0] = float(4)
a[1][1] = float(4)
a[2][0] = float(5)
a[2][1] = float(6)
```
Now we have 
```
a = [[1.0, 8.0], 
     [4.0, 4.0], 
     [5.0, 6.0]]
     
e = [1, 1]
```
Let's create `c` as the transpose of matrix `a`.
```
c = mxv(a, e)
```
Now we have
```
c = [9.0, 8.0, 11.0]
```


**Implementation/Code:** The following is the code for mxv(m, v)
```
def mxv(m, v):
    if len(v) != len(m[1]):
        return "Error Invalid sizes!"
    
    z = [0 for i in range(0, len(m))]
    
    for i in range(0, len(m)):
        for j in range(0, len(m[1])):
            z[i] = z[i] + m[i][j] * v[j]
            
    return z
```

**Last Modified:** December 2018

