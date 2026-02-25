# notes-oops-cons-decons
# notes-oops-cons-decons

## Constructor

A constructor is used to initialize the values of an object's data members at the time of object creation. It is automatically called when an object of the class is created.

### Example

```cpp
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
