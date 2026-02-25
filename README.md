# notes-oops-cons-decons
Constructor

Constructor

A constructor is used to initialize the values of an object's data members at the time of object creation.
It is automatically called when an object of the class is created.

Example:
class Student {
    // Data members
    string gender;
    int age;

public:
    // Constructor
    Student(string g, int a) {
        gender = g;
        age = a;
    }
};

In this example, the constructor initializes the gender and age of a Student object when it is created.
