# Change of Basis

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** basis

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This takes a pair of vectors and computes a pair of orthogonal unit vectors. 

**Input:** Two vector arrays of numbers of the same length.

**Output:** This doesn't return any value, but changes the vector arrays given as input because the parameters are passed by reference in python.

**Usage/Example:** 
First define two vectors
```
c = [float(0) for i in range(0, 3)]
d = [float(0) for i in range(0, 3)]

c[0] = 1.5
c[1] = 9.4
c[2] = 3.3

d[0] = 1
d[1] = 9
d[2] = 3
```
Print out the computation of our method given the methods.
```
print(basis(c, d))
```
This changes the vector arrays to
```
c = [0.7071067811865475, 0.5656854249492385, 0.42426406871192823]
d = [0.01098901098901099, 0.0989010989010989, 0.03296703296703297]
```


**Implementation/Code:** The following is the code for basis(u, v)
```
def basis(u, v):
    dot = [0.0 for i in range(len(v))]
    
    sumVal = 0.0
    for i in range(len(v)):
        sumVal = sumVal + (u[i] * v[i])
        
    sumVal2 = 0.0
    for i in range(len(v)):
        sumVal2 = sumVal2 + (v[i] * v[i])
        
    sumVal = sumVal / sumVal2
    
    for i in range(len(v)):
        dot[i] = sumVal * v[i]
        
    for i in range(len(v)):
        u[i] = u[i] - v[i]
        
    sumVal = 0.0
    sumVal2 = 0.0
    
    for i in range(len(u)):
        sumVal = sumVal + (u[i]**2)
        sumVal2 = sumVal2 + (v[i]**2)
        
    sumVal = math.sqrt(sumVal)
    
    for i in range(len(u)):
        u[i] = u[i]/sumVal
        v[i] = v[i]/sumVal2
        
    return
```

**Last Modified:** December 2018
