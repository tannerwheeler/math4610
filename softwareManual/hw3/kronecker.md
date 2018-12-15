# The Kronecker Product

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** kroneckerprod

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This method will perform the kronecker product on an mxn matrix onto an qxp matrix.

**Input:** The two inputs should be two dimensional arrays.

**Output:** The method will return a two dimensional array of dimensions (m * q)x(n * p).

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
c = kroneckerprod(a, b)
```
We now have
```
c = [[3.0, 1.0, 3.0, 24.0, 8.0, 24.0],
     [1.0, 0.0, 2.0, 8.0, 0.0, 16.0],
     [12.0, 4.0, 12.0, 12.0, 4.0, 12.0],
     [4.0, 0.0, 8.0, 4.0, 0.0, 8.0],
     [15.0, 5.0, 15.0, 18.0, 6.0, 18.0],
     [5.0, 0.0, 10.0, 6.0, 0.0, 12.0]]
```


**Implementation/Code:** The following is the code for kroneckerprod(x, y)
```
def kroneckerprod(x,y):
    z = [[0.0] * (len(x[1])*len(y[0])) for k in range(0,len(x)*len(y))]
    
    iterRow = 0 # The Row being computed in the product
    for i in range(0, len(x)):        
        for k in range(0, len(y)):
            iterCol = 0 # The Column being computed in the product
            
            for j in range(0, len(x[i])):
                for l in range(0, len(y[k])):
                    
                    z[iterRow][iterCol] = 0.0 + x[i][j] * y[k][l]
                    iterCol = iterCol + 1 
                    
            iterRow = iterRow + 1

    return z
```

**Last Modified:** December 2018
