# bcs231001-task1
25/12/2023

#include <iostream>
using namespace std;
class Shape {
public:
    
    virtual double calculateArea() const = 0;
    virtual ~Shape() {}
};
class Circle : public Shape {
private:
    double radius;

public:
    
    Circle(double r)
        : radius(r) {}

    
    double calculateArea() const override {
        return 3.14159 * radius * radius;
    }
};


class Rectangle : public Shape {
private:
    double length;
    double width;

public:

    Rectangle(double l, double w) : length(l), width(w) {}
    double calculateArea() const override {
        return length * width;
    }
};

int main() {
    
    Circle circle(5.0);
    Rectangle rectangle(4.0, 6.0);

    
    Shape* shape1 = &circle;
    Shape* shape2 = &rectangle;

    
    cout << "Area of Circle: " << shape1->calculateArea() << endl;
    cout << "Area of Rectangle: " << shape2->calculateArea() << endl;

    return 0;
}
