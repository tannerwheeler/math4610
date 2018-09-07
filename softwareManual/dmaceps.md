# Double Precision Machine Epsilon

**Routine Name:**           dmaceps

**Author:** Tanner Wheeler

**Language:** C. The code can be compiled using the GNU gcc compiler (gcc).

For example,

    gcc smaceps.c -o MachineEps

will produce an executable which can be run by

    ./MachineEps

**Description/Purpose:** This routine will compute the double precision value for the machine epsilon.

**Input:** There are no inputs needed.

**Output:** This routine returns an integer value of the double precision value for the machine epsilon.

**Usage/Example:**
This function must be called from the main function or another function. For example:

```
int main()
{
  int precision = dmaceps();
  
  printf("%i\n", precision);
  
  return 0;
}
```
This code will print
```
53 (or some other number depending on the machine)
```
to the console.

**Implementation/Code:** The following is the code for dmaceps()
```
int dmaceps(){
    float one = 1.0;
    double seps = 1.0;
    double appone = one + seps;

    int power = 0;

    double test = fabs(appone - one);
    while(test != 0.0)
    {
        power = power + 1;

        seps = seps / 2;
        appone = one + seps;

        test = fabs(appone - one);
    }
    
    return power;
}
```
**Last Modified:** September/2018
