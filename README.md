#include <iostream>

class Complex {
private:
    double real;
    double imag;
public:
    // Constructor
    Complex(double r = 0.0, double i = 0.0) : real(r), imag(i) {}
    
    // Getter functions
    double getReal() const { return real; }
    double getImag() const { return imag; }
    
    // Overloading binary addition operator (+) as a friend function
    friend Complex operator+(const Complex& c1, const Complex& c2);
};

// Definition of overloaded addition operator
Complex operator+(const Complex& c1, const Complex& c2) {
    return Complex(c1.real + c2.real, c1.imag + c2.imag);
}

int main() {
    Complex a(3.0, 4.0);
    Complex b(1.5, 2.5);
    
    Complex c = a + b; // Uses overloaded addition operator
    
    std::cout << "Result of addition: " << c.getReal() << " + " << c.getImag() << "i" << std::endl;

    return 0;
}
