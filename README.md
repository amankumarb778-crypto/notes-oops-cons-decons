

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


#### **Types of Constructors**

---

#### **1.1 Default Constructor**
A default constructor is a constructor that takes no arguments. It initializes an object with default values.

**Example from CodingGita:**  
In the CodingGita BTech program, imagine a scenario where we create a default student profile.

```cpp
#include <iostream>
using namespace std;

class Student {
private:
    string name;
    int rollNumber;

public:
    // Default Constructor
    Student() {
        name = "Unknown";
        rollNumber = 0;
    }

    void display() {
        cout << "Name: " << name << ", Roll Number: " << rollNumber << endl;
    }
};

int main() {
    Student student1; // Default constructor is called
    student1.display();
    return 0;
}
```

**Output:**
```
Name: Unknown, Roll Number: 0
```

---

#### **1.2 Parameterized Constructor**
A parameterized constructor takes arguments and allows the programmer to initialize objects with specific values.

**Example from CodingGita:**  
Imagine assigning details to a student in CodingGita's database.

```cpp
#include <iostream>
using namespace std;

class Student {
private:
    string name;
    int rollNumber;

public:
    // Parameterized Constructor
    Student(string n, int r) {
        name = n;
        rollNumber = r;
    }

    void display() {
        cout << "Name: " << name << ", Roll Number: " << rollNumber << endl;
    }
};

int main() {
    Student student1("Yashvi", 101);
    Student student2("Mahir", 102);

    student1.display();
    student2.display();

    return 0;
}
```

**Output:**
```
Name: Yashvi, Roll Number: 101
Name: Mahir, Roll Number: 102
```

---

#### **1.3 Copy Constructor**
A **copy constructor** creates a new object as a copy of an existing object. The default copy constructor provided by the compiler performs a shallow copy, which can lead to issues when the object contains dynamically allocated memory or other non-trivial resources. Defining a custom copy constructor allows for a deep copy, ensuring proper duplication of all resources owned by the original object.

**Why do we need a copy constructor?**
- To avoid sharing memory between objects, which can lead to data corruption or memory errors.
- To ensure proper duplication of dynamically allocated resources.

- **Shallow Copy**: Copies the memory addresses (pointers) instead of the actual data. If one object changes the data, it affects the other because both objects share the same memory. **(Default behavior of copy constructor)**

- **Deep Copy**: Creates a new copy of the data in a different memory location. Both objects have their own separate copies of the data, avoiding unintended changes. **(Requires a custom copy constructor)**

---

**Example from CodingGita: Deep Copy Implementation**

```cpp
#include <iostream>
using namespace std;

class Student {
private:
    string name;
    int mark1, mark2; // Separate variables for marks

public:
    // Parameterized Constructor
    Student(string n, int m1, int m2) : name(n), mark1(m1), mark2(m2) {}

    // Copy Constructor
    Student(const Student &s) : name(s.name), mark1(s.mark1), mark2(s.mark2) {}

    void display() {
        cout << "Name: " << name << ", Marks: " << mark1 << ", " << mark2 << endl;
    }
};

int main() {
    Student student1("Arjun", 85, 90);

    Student student2 = student1; // Copy constructor is called

    student1.display();
    student2.display();

    return 0;
}

```

**Output:**
```
Name: Arjun, Marks: 85 90 95 
Name: Arjun, Marks: 85 90 95 
```
