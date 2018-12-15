# Determinant of a Matrix

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** det

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This will find the determinant of a given square matrix.

**Input:** The only input is a two dimensional array with dimensions nxn.

**Output:** This will return a double value representing the determinant.  If a non square matrix is inputed it will return an error message.

**Usage/Example:**
First let's define `a`.
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
```
Now we have
```
a = [[1.0, 8.0, 2.0],
     [4.0, 4.0, 1.0],
     [5.0, 6.0, 2.0]]
```
If we print the output of our method
```
print(det(a))
```
The value
```
-14.0
```
will be printed to the console.


**Implementation/Code:** The following is the code for det(a)
```
def det(a):
    comatrix = [[0.0] * (len(a[0])-1) for k in range(0, len(a)-1)]
    
    if len(a) != len(a[0]):
        return "Error, Not a Square matrix"
    
    det = 0.0
    
    if len(a) == 2:
        return (a[0][0]*a[1][1]) - (a[0][1]*a[1][0])
    
    sign = -1
    for i in range(0, len(a[0])):
        for k in range(1, len(a)):
            for j in range(0, i):
                comatrix[k-1][j] = 0.0 + a[k][j]
            for j in range(i+1, len(a[0])):
                comatrix[k-1][j-1] = 0.0 + a[k][j]

        det = det + (sign)**i * a[0][i] * determinant(comatrix)                 
    
    return det
```

**Last Modified:** December 2018
