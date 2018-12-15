# Power Method

**Routine Name:** powermethod

**Author:** Tanner Wheeler

**Language:** C++.  This can be compiled using the GNU compiler.  On the command line when in the file containing the code use the command
```
g++ ./<fileNameHere>.cpp 
```
This will create a `a.out` file.  To run the program use the command
```
./a
```

**Description/Purpose:** This will perform the Power Method on a matrix.  This will find the largest eigenvalue of the matrix.  The matrix must be symmetric positive definite.

**Input:** This method takes a two dimensional vector array as input the first input.  Dimensions need to be nxn.  The second input needs to be a vector of length n. The dimensions need to be checked before calling the method.

**Output:** This will return a double number value representing the largest eigenvalue.

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

	std::cout << powermethod(a, b, 15, .0001) << std::endl;

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
Our output for the powermethod method will be
```
16.156375178341705
```


**Implementation/Code:** The following is the code for powermethod(a, b, maxiter, tol)
```
double powermethod(std::vector<std::vector<double>> a, std::vector<double> b, int maxiter, double tol)
{
	double error = tol * 10;
	double eigen0 = 0.0;
	int k = 0;
	int n = b.size();

	std::vector<double> y = b;

	int i, j;
	double sum;
	for (i = 0; i < n; i++)
	{
		sum = 0.0f;
		for (j = 0; j < n; j++)
		{
			sum += a[i][j] * b[j];
		}
		y[i] = sum;
	}

	while (error > tol && k < maxiter)
	{
		int i, j;
		double sum;
		
		double norm2vec = 0.0f;

		for (i = 0; i < n; i++)
		{
			norm2vec += (y[i] * y[i]);
		}

		norm2vec = sqrt(norm2vec);

		for (i = 0; i < n; i++)
		{
			y[i] *= (1 / norm2vec);
		}

		std::vector<double> z = b;

		for (i = 0; i < n; i++)
		{
			sum = 0.0f;
			for (j = 0; j < n; j++)
			{
				sum += a[i][j] * y[j];
			}
			z[i] = sum;
		}


		double eigen1 = 0.0f;

		for (i = 0; i < n; i++)
		{
			eigen1 += y[i] * z[i];
		}

		error = std::abs(eigen1 - eigen0);

		eigen0 = eigen1;
		k++;

		for (i = 0; i < n; i++)
		{
			y[i] = z[i];
		}
	}

	return eigen0;
}
```

**Last Modified:** December 2018

