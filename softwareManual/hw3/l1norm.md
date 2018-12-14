# L1 Vector Norm

**Routine Name:** norm1vec

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** 

**Input:** 

**Usage/Example:**
```
c = [float(0) for i in range(0, 3)]

c[0] = 1
c[1] = 9
c[2] = 3

print(norm1vec(c))
```
This would print
```
13.0
```
to the console.

**Implementation/Code:** The following is the code for norm1vec(x)
```
def norm1vec(x):
    numSum = 0.0
    for i in x:
        numSum = numSum + abs(i)
        
    return numSum
```

**Last Modified:** Dec 13, 2018

