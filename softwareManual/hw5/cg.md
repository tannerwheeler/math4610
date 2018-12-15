# Conjugate Gradient Method

[GO BACK TO SOFTWARE MANUAL](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)

**Routine Name:** conGrad

**Author:** Tanner Wheeler

**Language:** C++.  This can be compiled using the GNU compiler.  On the command line when in the file containing the code use the command
```
g++ ./<fileNameHere>.cpp 
```
This will create a `a.out` file.  To run the program use the command
```
./a
```

**Description/Purpose:** This method will run the Conjugate Gradient method on a matrix that is symmetric and positive definite.

**Input:** Given the equation `Ax = b`.  A two dimensional vector array is the first input representing `A`.  It has dimensions nxn.  The second is a vector array of length n representing `b`. The third input is a vector array of length n representing a guess of `x`.  The fourth is an integer of the maximum number of times the method should iterate.  The last input is a small double number for the amount of error allowed for the answer.

**Output:** This will output the solution `x` that satisfies the equation `Ax=b`.  It will be a vector array of length n.

**Usage/Example:**
In our main function we want to create a two dimension vector array `a`, vector array `b`, vector array `x0` as a guess, use 15 for maxiter, and .0001 for tol.

```
#include<vector>
#include<iostream>

int main(void)
{
	int n = 3;

	std::vector<double> b(n);
	std::vector<double> x(n);

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
  
	for (int i = 0; i < x.size(); i++)
	{
		x[i] = 0.0; //Our guess will be a vector of zeros
	}

	std::cout << conGrad(a, b, x, 15, .0001) << std::endl;

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
Our output for the Conjugate Gradient method will be
```
[0.9999641037446935, 1.0000164852836104, 0.999989210187439]
```


**Implementation/Code:** The following is the code for conGrad(a, b, x0, maxiter, tol)
```
std::vector<double> conGrad(std::vector<std::vector<double>> a, std::vector<double> b, std::vector<double> x0, int maxiter, double tol)
{
	int k = 0;
	int n = b.size();

	std::vector<double> x1 = x0;

	std::vector<double> p0 = b;
	std::vector<double> r0 = b;

	
	int i,j;
	double sum;
	for (i = 0; i < n; i++)
	{
		sum = 0.0f;
		for (j = 0; j < n; j++)
		{
			sum += a[i][j] * x0[j];
		}
		p0[i] -= sum;
		r0[i] -= sum;
	}

	double delta0 = 0.0f;
	double bdelta = 0.0f;
	for (int i = 0; i < n; i++)
	{
		delta0 += p0[i] * p0[i];
		bdelta += b[i] * b[i];
	}

	while (delta0 > ((tol * tol) - bdelta) && k < maxiter)
	{
		std::vector<double> s = b;

		int i,j;
		double sum;
			#pragma omp parallel for shared(p0, a, s, n) private(i, j)

		for (i = 0; i < n; i++)
		{
			s[i] = 0.0;
			for (j = 0; j < n; j++)
			{
				s[i] += a[i][j] * p0[j];
			}
		}
		
		double ynorm = 0.0f;

		int i;
		for (i = 0; i < n; i++)
		{
			ynorm += p0[i] * s[i];
		}

		double alpha = delta0 / ynorm;


		
		int i;
		for (i = 0; i < n; i++)
		{
			x1[i] = 0.0;
			x1[i] = x0[i] + (p0[i] * alpha);
		}

		std::vector<double> r1 = b;

		int i;
		for (i = 0; i < n; i++)
		{
			r1[i] = r0[i] - (s[i] * alpha);
		}

		double delta1 = 0.0f;

		int i;
		for (i = 0; i < n; i++)
		{
			delta1 += r1[i] * r1[i];
		}

		std::vector<double> p1 = b;

		int i;
		for (i = 0; i < n; i++)
		{
			p1[i] = r1[i] + (p0[i] * (delta1/delta0));
		}

		k++;


		
		int i;
		for (i = 0; i < n; i++)
		{
			r0[i] = r1[i];
			p0[i] = p1[i];
			x0[i] = x1[i];
		}

		delta0 = delta1;
	}

	return x0;
}

```

**Last Modified:** December 2018
