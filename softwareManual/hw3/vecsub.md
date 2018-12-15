# Vector Subtraction

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** subtractvectors

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This method will subtract two vectors of the same length and create a new vector from their subtration.

**Input:** There are two inputs for this method.  Both are vectors of the same length, but may contain different values.

**Output:** This will return the new vector that is the subtraction of the input vectors. 

**Usage/Example:** First let's create two vectors `c` and `d` of size 3 and set each element to a specific number.
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
Now let's print out the value return from our function given our created vectors.
```
print(subtractvectors(c, d))
```
This will print
```
[0.5, 0.40000000000000036, 0.2999999999999998]
```
to the console.

**Implementation/Code:** The following is the code for addvectors(x, y)
```
def subtractvectors(x, y):
    if len(x) != len(y):
        return "Error inconsistent lengths!"
    
    newVector = [0 for i in range(0, len(x))]
    
    for i in range(0, len(x)):
        newVector[i] = x[i] - y[i]
        
    return newVector
```

**Last Modified:** December 2018
