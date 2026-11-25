Single and Multilevel Inheritance


#include <iostream>
using namespace std;


class Person {
public:
    string name;
    int age;

    void getPerson() {
        cout << "Enter name: ";
        cin >> name;
        cout << "Enter age: ";
        cin >> age;
    }
};

class Student : public Person {
public:
    int rollNo;

    void getStudent() {
        cout << "Enter roll number: ";
        cin >> rollNo;
    }

    void displayStudent() {
        cout << "\n--- Single Inheritance ---" << endl;
        cout << "Name: " << name << endl;
        cout << "Age: " << age << endl;
        cout << "Roll Number: " << rollNo << endl;
    }
};


class Vehicle {
public:
    string brand;

    void getVehicle() {
        cout << "\nEnter vehicle brand: ";
        cin >> brand;
    }
};

class Car : public Vehicle {
public:
    string model;

    void getCar() {
        cout << "Enter car model: ";
        cin >> model;
    }
};

class ElectricCar : public Car {
public:
    int battery;

    void getElectricCar() {
        cout << "Enter battery capacity (kWh): ";
        cin >> battery;
    }

    void displayElectricCar() {
        cout << "\n--- Multilevel Inheritance ---" << endl;
        cout << "Brand: " << brand << endl;
        cout << "Model: " << model << endl;
        cout << "Battery Capacity: " << battery << " kWh" << endl;
    }
};

int main() {
    Student s;
    s.getPerson();
    s.getStudent();
    s.displayStudent();

    ElectricCar e;
    e.getVehicle();
    e.getCar();
    e.getElectricCar();
    e.displayElectricCar();

    return 0;
}



