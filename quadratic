#include <iostream>
#include <math.h>

struct quadratic_data
{
    double a = 0;
    double b = 0;
    double c = 0;
    
    int number_of_roots = -1;
    
    double x1 = 0;
    double x2 = 0;
    double zero =0.00000001;
};

void input (quadratic_data * qd)
{
    std::cout << "Quadratic - ax^2 + bx + c = 0. Choose a, b, c:" << std::endl;
    std::cout << " a = ";
    std::cin >> qd -> a;
    std::cout << " b = ";
    std::cin >> qd -> b;
    std::cout << " c = "; 
    std::cin >> qd -> c;
}

void resolution_lin (quadratic_data * qd)
{ 
    double b = qd -> b;
    double c = qd -> c;
    
    double zero = qd -> zero;
    
    if (abs(b) > zero)
    {
        qd -> x1 = -c/b;
        qd -> number_of_roots = 1;
        return;
    } 
    else
    {
        if (abs(c) > 0)
        {
            qd -> number_of_roots = 0;
            return;
        }
        else
        {
            qd -> number_of_roots = 404;
            return ;
        }
    }
}

void resolution_quadratic (quadratic_data * qd)
{
    double a = qd -> a;
    double b = qd -> b;
    double c = qd -> c;
    
    double D = b*b - 4*a*c;
    double zero = qd -> zero;
    
    if (abs(a) > zero)
    {
        if (D > zero)
        {
            qd -> x1 = -b/(2*a) + sqrt(b*b - 4*a*c)/(2*a);
            qd -> x2 = -b/(2*a) - sqrt(b*b - 4*a*c)/(2*a);
            qd -> number_of_roots = 2;
            return;
        }
        if (abs(D) <= zero)
        {
            qd -> x1 = -b/(2*a);
            qd -> number_of_roots = 1;
            return;
        }
        if (D < -zero);
        {
            qd -> number_of_roots = 0;
            return;
        }
    }
    else
    {
        resolution_lin (qd);
        return;
    }    
}

void output (quadratic_data * qd)
{
    int number_of_roots = qd -> number_of_roots;
   
    if (number_of_roots == 2)
    {
       
        std::cout << "x1 = " << qd -> x1 << std::endl;
        std::cout << "x2 = " << qd -> x2 << std::endl;
        return;
    }
    if (number_of_roots == 1)
    {
        std::cout << "x = " << qd -> x1;
        return;
    }
    if (number_of_roots == 0)
    {
        std::cout << "No roots";
        return;
    }
    if (number_of_roots == 404)
    {
        std::cout << "x = anyone";
        return;
    }
    return;
}

int main()
{
    quadratic_data qd1;
    input (&qd1);
    resolution_quadratic (&qd1);
    output (&qd1);
    return 0;
}
