# Dot Product (Inner Product)

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** innervectorprod

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This method will take the dot product of two vectors of the same length and return its value.

**Input:** The two input needed for this method are two vector arrays of the same length.

**Output:** This will return a double value of the dot product from the two inputs.  If the vectors aren't the same length then it will return an error message.

**Usage/Example:** 
First let's create two vectors `c` and `d` of size 3 and set each element to a specific number.
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
print(innervectorprod(c, d))
```
This will print
```
96.0
```
to the console.

**Implementation/Code:** The following is the code for innervectorprod(x, y)
```
def innervectorprod(x, y):
    if len(x) != len(y):
        return "Error inconsistent lengths!"
    
    numSum = 0.0
    for i in range(0, len(x)):
        numSum = numSum + (x[i] * y[i])
        
    return numSum
```

**Last Modified:** December 2018

