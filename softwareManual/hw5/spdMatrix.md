# Symmetric Positive Definite Matrix Creator

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** posdefMatrixCreator

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This method will create a Matrix that is Symmetric Positive Definite and a vector that is the result of multiplying the created matrix by a vector of just 1's.  This can be used for testing purposes

**Input:** The only input is the size of matrix that you want.

**Output:** The output will be a 2 part vector array of a two dimensional vector array and a 1 dimensional array.

**Usage/Example:**
```
a = posdefMatrixCreator(3)
```
This gives us
```
a[0] = [[15.0, 6, 8],
        [6, 8.0, 1],
        [8, 1, 10.0]]
        
a[1] = [29.0, 15.0, 19.0]
```


**Implementation/Code:** The following is the code for posdefMatrixCreator(n)
```
def posdefMatrixCreator(n):
    M = [[0.0] * n for k in range(0, n)]
    b = [0.0 for i in range(0, n)]
    
    for i in range(n):
        for j in range(i+1, n):
            M[i][j] = random.randint(0, 10)
            M[j][i] = M[i][j]
    
    for i in range(n):
        sumVal = 0.0
        for j in range(n):
            sumVal = sumVal + M[i][j]
        
        M[i][i] = sumVal + 1
        
    #print(M)
    
    for i in range(n):
        b[i] = 0.0
        for j in range(n):
            b[i] = b[i] + M[i][j]
            
    return M, b
```

**Last Modified:** December 2018

