

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
