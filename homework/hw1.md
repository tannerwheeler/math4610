## Homework #1
#### Tanner Wheeler

### 1. Problem: Write a code that will return machine precision for your computer (or any other computer for that matter) in single precision arithmetic. Give the method a name that is descriptive. For example, maceps(), or something like that. The routine should return the default machine precision. Create a second routine that will return the machine precision in double precision computations. Give the routine a unique name, say dmaceps(). Make sure that your code is fully documented with you as the author and so on. An example of a Fortran code is included in this repository. You can translate this into a Python, C, or C++ code to do the work. You can also modify the Fortran and use this directly.

#### Answer:
[Single Precision Machine Epsilon Code](https://tannerwheeler.github.io/math4610/softwareManual/smaceps)

[Double Precision Machine Epsilon Code](https://tannerwheeler.github.io/math4610/softwareManual/dmaceps)



### 2. Problem: Create a repository on [Github](https://www.github.com) and create a repositry for this homework that will contain a software manual for all the code you will write and work with in the course.

#### Answer:
[Software Manual](https://tannerwheeler.github.io/math4610/softwareManual/softwareManual)




### 3. Problem: Create a shared library from the routines you have created.

#### Answer:
```
A01770306@ENG30310 ~/hw1_prob3
$ gcc -c smaceps.c

A01770306@ENG30310 ~/hw1_prob3
$ ar crv testLibrary *.o
a - smaceps.o

A01770306@ENG30310 ~/hw1_prob3
$ ranlib testLibrary

A01770306@ENG30310 ~/hw1_prob3
$ ls
main.c  smaceps.c  smaceps.h  smaceps.o  testLibrary

```


### 4. Problem: In this problem you will learn a bit more about your computer and how many processes you can run on the cores included in your computer.

#### Answer:
This was the input.  I was on a computer in the Engineering computer lab.
```
	program main
	integer id, nthrds
	integer omp_get_thread_num, comp_get_num_threads
C$OMP	PARALLEL PRIVATE(id)
	id = omp_get_thread_num()
	print *, 'hello world from thread', id
C$OMP	BARRIER
	if(id .eq. 0) then
		nthrds = omp_get_num_threads()
		print *, 'There are', nthrds, ' threads!'
	end if
C$OMP	END PARALLEL
	stop
	end
```
This is the output
```
c hello world from thread           7
c hello world from thread           1
c hello world from thread           5
c hello world from thread           2
c hello world from thread           6
c hello world from thread           3
c hello world from thread           4
c hello world from thread           0
c There are           0  threads!
```


### 5. Problem: We will use Taylor series expansions in a lot of the work we do in Math 4610. Expand the following functions about the given center x_o.  Find the radius of convergence of each of the series.

#### Answer:
The Taylor Series expansions can be found on pages 1-3 on the [HW1.pdf](https://tannerwheeler.github.io/math4610/homework/HW1.pdf).

The Radius of Convergence for each of the series can be found on pages 4-6 of the [HW1.pdf](https://tannerwheeler.github.io/math4610/homework/HW1.pdf).


### 6. Problem: Compute the following antiderivatives.

#### Answer:
The Antiderivative Computations can be found on pages 7-9 of the [HW1.pdf](https://tannerwheeler.github.io/math4610/homework/HW1.pdf).


### 7. Problem: Write a routine that will return the roots of a quadratic polynomial in an array. Also, create a software manual entry for the routine and include this in your software manual.

#### Answer:
[Quadratic Polynomial Root Finder](https://tannerwheeler.github.io/math4610/softwareManual/roots)


### 8. Problem: Compute the solutions for the following simple initial value problems.

#### Answer:
The solutions to the initial value problems can be found on pages 10-11 of the [HW1.pdf](https://tannerwheeler.github.io/math4610/homework/HW1.pdf).



### 9. Problem: Search the internet for an application that is influenced by machine precision. Write a paragraph on one of the results you have found. Identify one and only one such web site. Make sure that you cite the web site appropriately.

#### Answer:
In an article from Siam News, written by Nicholas Higham, the history of machine precision in computers is discussed.  They talk about how computers only started with single precision and then double precision was introduced.  Even with double precision it didn't make things 100% better.  The amount of memory saved by single precision helped it get faster than double precision.  These computations became much faster when the Cell Processor for the Play Station 3 was created.  As manufacturers continue to improve their precision for different problems/designs we have today half precision and quadruple precision have been introduced.

Source:
Nicholas Higham, *A Multiprecision World*, Siam News, Oct. 2 2017, www.sinews.siam.org/Details-Page/a-multiprecision-world, Sept. 7 2018


## 10. Problem: Graph the solutions of the last two differential equations in the Problem above.

#### Answer:
The Graphs can be found on page 12 of the [HW1.pdf](https://tannerwheeler.github.io/math4610/homework/HW1.pdf).


