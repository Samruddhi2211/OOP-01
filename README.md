# OOP-01
PROBLEM STATEMENT:
Implement a class Complex which represents the Complex Number data type. Implement the
following operations:
1.Constructor (including a default constructor which creates the complex number 0+0i).
2.Overloaded operator+ to add two complex numbers.
3.Overloaded operator* to multiply two complex numbers.
4.Overloaded << and >> to print and read Complex Numbers.
*/
#include <iostream>
using namespace std;
class complex //class name complex is declared
{
float realp,imagp;
public:
complex() //default constructor
{
realp=0;
imagp=0;
}
complex operator+(complex &); //for addition of two complex nos
complex operator*(complex &); //for multiplication of two complex nos
complex(float,float); //parameterized constructor
friend istream &operator>>(istream &,complex &);
friend ostream &operator<<(ostream &,complex &);
};
complex::complex(float x,float y) //parameterized constructor definition
{
realp=x;
imagp=y;
}
//function to accept values of real and imag parts of complex no
istream &operator>>(istream &din,complex &c)
{
cout<<"Enter real part of complex number 2: ";
din>>c.realp;
cout<<"\nEnter imaginary part of complex number 2: ";
din>>c.imagp;
return din;
}
//functions to display complex nos
ostream &operator<<(ostream &dout , complex &c)
{
dout<<c.realp<<" + "<<c.imagp<<"i";
dout<<endl;
return dout;
}
//function to add two complex nos
complex complex::operator+(complex &c)
{
complex temp;
temp.realp=realp + c.realp;
temp.imagp=imagp + c.imagp;
return temp;
}
//function to multiply two complex nos
complex complex::operator*(complex &c)
{
complex mul;
mul.realp=(realp*c.realp) - ( imagp*c.imagp);
mul.imagp=(imagp*c.realp) + (realp*c.imagp);
return mul;
}
int main()
{
complex c2,c3;
complex c1(1.2,2.2);
cout<<"Complex no 1 is:"<<c1;
cout<<"Enter complex no 2:\n";
cin>>c2;
cout<<"Complex number 1 is :";
cout<<c1;
cout<<"Complex number 2 is :";
cout<<c2;
cout<<"Complex number 3 is :";
cout<<c3;
cout<<"\nAddition of two complex numbers is: ";
c3=c1+c2;
cout<<c3;
cout<<"\nMultiplication of two complex number is: ";
c3=c1*c2;
cout<<c3; //display value of c3
return 0;
}

/*
OUTPUT:
Complex no 1 is:1.2 + 2.2i
Enter complex no 2:
Enter real part of complex number 2: 1

Enter imaginary part of complex number 2: 2
Complex number 1 is :1.2 + 2.2i
Complex number 2 is :1 + 2i
Complex number 3 is :0 + 0i

Addition of two complex numbers is: 2.2 + 4.2i

Multiplication of two complex number is: -3.2 + 4.6i
