# Transpose of a Matrix

**Routine Name:** transpose

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This will find the transpose of a given matrix.

**Input:** This method takes one matrix as its only input.

**Output:** This method will return the transpose of the input matrix.

**Usage/Example:** 
First let's create a matrix `a` whose dimensions are 3x2 and set its values.
```
n = 2
m = 3

a = [[float(0)] * n for i in range(0,m)]

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
```
Let's create `c` as the transpose of matrix `a`.
```
c = transpose(a)
```
Now we have
```
c = [[1.0, 4.0, 5.0], 
     [8.0, 4.0, 6.0]]
```


**Implementation/Code:** The following is the code for transpose(x)
```
def transpose(x):    
    z = [[0] * len(x) for k in range(0,len(x[1]))]
    
    for i in range(0, len(x)):
        for j in range(0, len(x[i])):
            z[j][i] = x[i][j]
            
    return z
```

**Last Modified:** December 2018

