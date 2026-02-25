

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



```
## Destructor

destructor -> it is a kind of function but get call automatically by 'c++ 
compiler' when a particular object is get destory because of the block scope.
