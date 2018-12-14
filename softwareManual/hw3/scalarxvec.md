# Scalar Vector Multiplication

**Routine Name:** scalarmultivec

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This method will multiply a scalar into a vector array.

**Input:** There are two inputs for this method.  The first is vector.  The second is the scalar you want to multiply into the vector.

**Output:** This will return the new vector that is the scalar multiple of the input vector. 

**Usage/Example:** First let's create a vector `c` of size 3 and set each element to a specific number.
```
c = [float(0) for i in range(0, 3)]

c[0] = 1.5
c[1] = 9.4
c[2] = 3.3
```
Now let's print out the value return from our function given our created vectors.
```
print(scalarmultivec(c, 5))
```
This will print
```
[7.5, 47.0, 16.5]
```
to the console.

**Implementation/Code:** The following is the code for scalarmultivec(x, y)
```
def scalarmultivec(x, y):
    
    newVector = [0 for i in range(0, len(x))]
    
    for i in range(0, len(x)):
        newVector[i] = y * x[i]
        
    return newVector
```

**Last Modified:** December 2018
