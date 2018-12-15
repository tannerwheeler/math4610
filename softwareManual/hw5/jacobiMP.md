# Jacobi Iterative Method OpenMP

**Routine Name:** jacobiMP

**Author:** Tanner Wheeler

**Language:** C++.  This can be compiled using the GNU compiler.  On the command line when in the file containing the code use the command
```
g++ -fopenmp ./<fileNameHere>.cpp 
```
This will create a `a.out` file.  To run the program use the command
```
./a
```

**Description/Purpose:** This method will run the Jacobi method, using parallelization, on a matrix that is symmetric and positive definite.

**Input:** Given the equation `Ax = b`.  A two dimensional vector array is the first input representing `A`.  It has dimensions nxn.  The second is a vector array of length n representing `b`. The third input is a vector array of length n representing a guess of `x`.  The fourth is an integer of the maximum number of times the method should iterate.  The last input is a small double number for the amount of error allowed for the answer.

**Output:** This will output the solution `x` that satisfies the equation `Ax=b`.  It will be a vector array of length n.

**Usage/Example:**
In our main function we want to create a two dimension vector array `a`, vector array `b`, vector array `x0` as a guess, use 150 for maxiter, and .0001 for tol.

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

	std::cout << jacobiMP(a, b, 150, .0001) << std::endl;

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
Our output for the jacobiMP method will be
```
[1.0000268759569217, 1.000023674136068, 1.0000113182069135]
```


**Implementation/Code:** The following is the code for jacobiMP(a, b, x0, maxiter, tol)
```
#include <vector>

std::vector<double> jacobiMP(std::vector<std::vector<double>> a, std::vector<double> b, std::vector<double> x0, int maxiter, double tol)
{
	int iter = 0;
	int n = b.size();

	double error = 10 * tol;
	std::vector<double> x1 = b;

	while (error > tol && iter < maxiter)
	{
		
		{
			int i,j;
			#pragma omp parallel for shared(x1, b, a, x0, n) private(i, j)

			for (i = 0; i < n; i++)
			{	

				x1[i] = 0.0f;
		
					for (j = 0; j < i; j++)
					{
						x1[i] += a[i][j] * x0[j];
					}

					for (j = i + 1; j < n; j++)
					{
						x1[i] += a[i][j] * x0[j];
					}

				x1[i] = (b[i] - x1[i]) / a[i][i];
			}
		}

		iter++;

		double sum = 0.0f;
		
		{
			int j;
			#pragma omp parallel private(j)
			{
				#pragma omp for
				for (j = 0; j < n; j++)
					sum += (x1[j] - x0[j]) * (x1[j] - x0[j]);
			}
		}

		error = sqrt(sum);

		{
			int i;
			#pragma omp parallel private(i)
			{
				#pragma omp for
				for (i = 0; i < n; i++)
				{
					x0[i] = x1[i];
				}
			}
		}
	}

	return x0;
}
```

**Last Modified:** December 2018
