# Matrix Addition

**Routine Name:** addMatrix

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This method will add two matrices together that have the same dimensions mxn.

**Input:** The two inputs will be two two dimensional arrays of dimensions mxn.

**Output:** The output will be a new matrix that is the addition of the two input arrays which will also be a two dimensional array.  If the dimensions aren't consistent for the inputs then the method will return an error message.

**Usage/Example:**
First let's create two matrices `a` and `b` whose dimensions are 3x2 and set there values.
```
n = 2
m = 3

a = [[float(0)] * n for i in range(0,m)]
b = [[float(0)] * n for i in range(0,m)]

a[0][0] = float(1)
a[0][1] = float(8)
a[1][0] = float(4)
a[1][1] = float(4)
a[2][0] = float(5)
a[2][1] = float(6)

b[0][0] = float(3)
b[0][1] = float(1)
b[1][0] = float(1)
b[1][1] = float(0)
b[2][0] = float(3)
b[2][1] = float(2)
```
Now we have 
```
a = [[1.0, 8.0], 
     [4.0, 4.0], 
     [5.0, 6.0]]
     
b = [[3.0, 1.0],
     [1.0, 0.0],
     [3.0, 2.0]]
```
Let's print the output of our method given the matrices.
```
print(addMatrix(a, b))
```
This prints
```
[[4.0, 9.0], [5.0, 4.0], [8.0, 8.0]]
```
to the console.


**Implementation/Code:** The following is the code for addMatrix(x, y)
```
def addMatrix(x, y):
    if len(x) != len(y):
        return "Error Invalid sizes!"
    if len(x) != len(y):
        return "Error Invalid sizes!"
    
    z = [[0] * len(x[1]) for i in range(0,len(x))]
    
    for i in range(0, len(x)):
        for j in range(0, len(x[i])):
            z[i][j] = x[i][j] + y[i][j]
            
    return z
```

**Last Modified:** December 2018

