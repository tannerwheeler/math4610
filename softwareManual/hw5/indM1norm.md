# Induced L1 Matrix Norm

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** induced1norm

**Author:** Tanner Wheeler

**Language:** Python. This code can be run on a python 3 compiler. The file can be imported and then the method will run.

**Description/Purpose:** This will compute the L1 Matrix Norm given a matrix and a vector.

**Input:** The first input is a two dimensional vector array of dimensions nxn.  The second input is a vector array of length n.

**Output:** This outputs a double number representing the value of the Induced L1 Matrix Norm.

**Usage/Example:**
First define a `a` and `d`
```
a = [[float(0)] * n for i in range(0,m)]
d = [float(0) for i in range(0, 3)]

d[0] = 1
d[1] = 9
d[2] = 3

a[0][0] = float(1)
a[0][1] = float(8)
a[0][2] = float(2)
a[1][0] = float(4)
a[1][1] = float(4)
a[1][2] = float(1)
a[2][0] = float(5)
a[2][1] = float(6)
a[2][2] = float(2)
```
Now use `a` and `d` and print out the result of our method
```
print(induced1norm(a, d))
```
This prints
```
14.384615384615385
```


**Implementation/Code:** The following is the code for induced1norm(a, b)
```
def induced1norm(a, b):
    return norm1vec(mxv(a,b))/norm1vec(b)
```

**Last Modified:** December 2018

