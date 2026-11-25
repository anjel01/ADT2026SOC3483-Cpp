Multiple and Hierarchical Inheritance


#include <iostream>
using namespace std;


class PersonalDetails {
public:
    string name;
    int age;

    void getPersonalDetails() {
        cout << "Enter employee name: ";
        cin >> name;
        cout << "Enter age: ";
        cin >> age;
    }
};

class SalaryDetails {
public:
    float salary;

    void getSalaryDetails() {
        cout << "Enter salary: ";
        cin >> salary;
    }
};

class Employee : public PersonalDetails, public SalaryDetails {
public:
    void displayEmployee() {
        cout << "\n--- Multiple Inheritance ---" << endl;
        cout << "Name: " << name << endl;
        cout << "Age: " << age << endl;
        cout << "Salary: " << salary << endl;
    }
};
class Shape {
public:
    void displayShape() {
        cout << "\n--- Hierarchical Inheritance ---" << endl;
        cout << "This is a shape." << endl;
    }
};

class Circle : public Shape {
public:
    float radius;

    void getCircle() {
        cout << "\nEnter circle radius: ";
        cin >> radius;
    }

    void areaCircle() {
        cout << "Area of Circle: "
             << 3.14 * radius * radius << endl;
    }
};

class Rectangle : public Shape {
public:
    float length, breadth;

    void getRectangle() {
        cout << "\nEnter length and breadth: ";
        cin >> length >> breadth;
    }

    void areaRectangle() {
        cout << "Area of Rectangle: "
             << length * breadth << endl;
    }
};

int main() {
    Employee e;
    e.getPersonalDetails();
    e.getSalaryDetails();
    e.displayEmployee();

    Circle c;
    c.displayShape();
    c.getCircle();
    c.areaCircle();

    Rectangle r;
    r.displayShape();
    r.getRectangle();
    r.areaRectangle();

    return 0;
}
