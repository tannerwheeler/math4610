# L1 Vector Norm

**Routine Name:** norm1vec

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This code will compute the l_1 norm of a vector.  This can be run for any size of vector with integer, float, and double values.  The method will return a double value for the l_1 norm.

**Input:** The input for this method is a 1 dimensional vector/list of numbers.

**Usage/Example:**
First let's create a vector `c` of size 3 and set each element to a specific number.
```
c = [float(0) for i in range(0, 3)]

c[0] = 1
c[1] = 9
c[2] = 3
```
Now let's print out the value return from our function given our created vector.
```
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

**Last Modified:** Dec 14, 2018

