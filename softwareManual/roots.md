# Quadratic Polynomial Root Finder

**Routine Name:**           rootFinder

**Author:** Tanner Wheeler

**Language:** C++. The code can be compiled using the GNU Fortran compiler (gfortran).

For example use,

    sudo g++ -o rootFinder rootFinder.cpp

will produce an executable that can be executed with the command

    ./rootFinder

**Description/Purpose:** This routine will compute the roots of a quadratic polynomial **ax^2 + bx + c = 0**.

**Input:** Three inputs are needed **a**, **b**, and **c** from **ax^2 + bx + c = 0**.

**Output:** This routine returns a vector with two strings.  The data is stored as strings for when the root is a complex number.

**Usage/Example:**
This function will be used when computing the roots of a quadratic polynomial.  This function must be called from the main or other function.  For example:
```
int main() {
    std::vector<std::string> rootArray;

    rootArray = rootFinder(1,5,4);

    std::cout << "Root 1 = " + rootArray[0] + "\t Root 2 = " + rootArray[1] << std::endl;

    return 0;
}
```
This is finding the roots of the polynomial **x^2 + 5x + 4 = 0**.  This will print to the console
```
Root 1 = -1.000000       Root 2 = -4.000000
```

**Implementation/Code:** The following is the code for rootFinder(double a, double b, double c)
```
std::vector<std::string> rootFinder(double a, double b, double c)
{
    std::vector<std::string> rootArray(2);

    double discriminant = b*b - (4*a*c);

    if(discriminant >= 0.0) // if the roots are real numbers
    {
        rootArray[0] = std::to_string(((-1 * b) + std::sqrt(discriminant))/(2*a));
        rootArray[1] = std::to_string(((-1 * b) - std::sqrt(discriminant))/(2*a));
    }
    else
    {
        discriminant = std::sqrt(-1 * discriminant);
        double img = discriminant/(2*a);
        double std = (-1 * b)/(2*a);

        if(std != 0.0) // if it is a complex number
        {
            img *= -1;
            rootArray[0] = std::to_string(std) + " + " + std::to_string(img) + "i";
            rootArray[1] = std::to_string(std) + " - " + std::to_string(img) + "i";
        }
        else // If it is only the imaginary number
        {
            img *= -1;
            rootArray[0] = std::to_string(img) + "i";
            rootArray[1] = "-" + std::to_string(img) + "i";
        }
    }

    return rootArray;
}
```
**Last Modified:** September/2018

