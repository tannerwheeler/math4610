# L-Infinity Vector Norm

**Routine Name:** normInfvec

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This code will compute the l_infinity norm of a vector. This can be run for any size of vector with integer, float, and double values.

**Input:** The input for this method is a 1 dimensional vector/list of numbers.

**Output:** This routine returns a double precision value for the l_infinity norm.

**Usage/Example:**
First let's create a vector `c` of size 3 and set each element to a specific number.
```
c = [float(0) for i in range(0, 3)]

c[0] = 1.5
c[1] = 9.4
c[2] = 3.3
```
Now let's print out the value returned from our function given our created vector.
```
print(normInfvec(c))
```
This will print
```
9.4
```
to the console.


**Implementation/Code:** The following is the code for normInfvec(x)
```
def normInfvec(x):
    max = 0.0
    for i in x:
        if max < abs(i):
            max = abs(i)
            
    return max
```

**Last Modified:** Dec 14, 2018

