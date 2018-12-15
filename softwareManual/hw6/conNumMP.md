# 2-Condition Matrix Norm Using OpenMP

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** cond2MP

**Author:** Tanner Wheeler

**Language:** C++.  This can be compiled using the GNU compiler.  On the command line when in the file containing the code use the command
```
g++ -fopenmp ./<fileNameHere>.cpp 
```
This will create a `a.out` file.  To run the program use the command
```
./a
```

**Description/Purpose:** This method will compute the 2-condition matrix norm of a matrix, using parallelization.  This method will use the methods [powermethodMP](https://tannerwheeler.github.io/math4610/softwareManual/hw5/powerMethodMP) and [invpowermethodMP](https://tannerwheeler.github.io/math4610/softwareManual/hw5/invpowerMethodMP).

**Input:** The first input is a two dimensional vector array of numbers.  The second input is a vector array of length n.  The third will be an integer for the maximum number of iterations.  The fourth input is the error allowed for the answer.

**Output:** This will return a float number representing the condition number.

**Usage/Example:**
In our main function we want to create a two dimension vector array `a`, vector array `b`, use 15 for maxiter, and use .0001 for tol.

```
#include<vector>
#include<iostream>

int main(void)
{
	int n = 3;

	std::vector<double> b(n);

  std::vector<std::vector<double>> a(n, std::vector<double>(n))

  a[0][0] = 7.0
  a[0][1] = 3.0
  a[0][2] = 1.0
  a[1][0] = 3.0
  a[1][1] = 10.0
  a[1][2] = 2.0
  a[2][0] = 1.0
  a[2][1] = 2.0
  a[2][2] = 15.0

  b[0] = 11.0
  b[1] = 15.0
  b[2] = 18.0

	std::cout << cond2MP(a, b, 15, .0001) << std::endl;

	return 0;
}  
```
You have created 
```
a = [[7.0, 3.0, 1.0],
     [3.0, 10.0, 2.0],
     [1.0, 2.0, 15.0]]
     
b = [11.0, 15.0, 18.0]
```
Our output for the cond2MP method will be
```
112.79883363958864
```


**Implementation/Code:** The following is the code for cond2MP(a, b, maxiter, tol)
```
double cond2MP(std::vector<std::vector<double> a, std::vector<double> b, int maxiter, double tol)
{
  return powermethodMP(a, b, maxiter, tol) * invpowermethodMP(a, b, maxiter, tol)
}
```

**Last Modified:** December 2018

