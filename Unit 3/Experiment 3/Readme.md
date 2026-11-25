Hybrid Inheritance and Ambiguity Resolution


#include <iostream>
using namespace std;


class Student {
public:
    int rollNo;

    void getRollNo() {
        cout << "Enter Roll Number: ";
        cin >> rollNo;
    }

    void displayRollNo() {
        cout << "Roll Number: " << rollNo << endl;
    }
};


class Test : virtual public Student {
public:
    int marks;

    void getMarks() {
        cout << "Enter Marks: ";
        cin >> marks;
    }
};

// Virtual inheritance
class Sports : virtual public Student {
public:
    int score;

    void getScore() {
        cout << "Enter Sports Score: ";
        cin >> score;
    }
};

class Result : public Test, public Sports {
public:
    void displayResult() {
        cout << "\n--- Hybrid Inheritance ---" << endl;
        displayRollNo();
        cout << "Marks: " << marks << endl;
        cout << "Sports Score: " << score << endl;
        cout << "Total Score: " << marks + score << endl;
    }
};


class First {
public:
    void show() {
        cout << "This is First class." << endl;
    }
};

class Second {
public:
    void show() {
        cout << "This is Second class." << endl;
    }
};

class Third : public First, public Second {
public:
    void display() {
        cout << "\n--- Ambiguity Resolution ---" << endl;
        First::show();
        Second::show();
    }
};

int main() {
    Result r;

    r.getRollNo();
    r.getMarks();
    r.getScore();
    r.displayResult();

    Third t;
    t.display();

    return 0;
}
