# L2 Vector Norm

**Routine Name:** norm2vec

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This code will compute the l_2 norm of a vector. This can be run for any size of vector with integer, float, and double values.  The package `math` will need to be imported as shown in the implementation section.

**Input:** The input for this method is a 1 dimensional vector/list of numbers.

**Output:** This routine returns a double precision value for the l_2 norm.

**Usage/Example:**
First let's create a vector `c` of size 3 and set each element to a specific number.
```
c = [float(0) for i in range(0, 3)]

c[0] = 1.5
c[1] = 9.4
c[2] = 3.3
```
Now let's print out the value return from our function given our created vector.
```
print(norm2vec(c))
```
This would print
```
10.074720839804943
```
to the console.

**Implementation/Code:** The following is the code for norm2vec(x)
```
import math

def norm2vec(x):
    numSum = 0.0
    for i in x:
        numSum = numSum + (abs(i)**2)
    
    return math.sqrt(numSum)
```

**Last Modified:** Dec 14, 2018

