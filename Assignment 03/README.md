# Assignment No: 03
# Date of Submission :15-10-2024
# Title : Find out the error in code with reason and Fix it
## Operator Overloading
## Problem No : 01 
Overload the >> and << shift operator relative to the coord class so that the following
types of operations are allowed:

ob << integer
ob >> integer

Make sure your operations shift the x and y values by the amount specified.

## Code :

```
#include <iostream>
using namespace std;
class coord {
    int x, y;
public:
    coord() { x = 0; y = 0; }
    coord(int i, int j) { x = i; y = j; }
    void get_xy(int &i, int &j) {
        i = x;
        j = y;
    }
    coord operator<<(int n) {
        x <<= n;
        y <<= n;
        return *this;
    }

    coord operator>>(int n) {
        x >>= n;
        y >>= n;
        return *this;
    }
};

int main() {
    coord obj(10, 20);
    int x, y;
    obj = obj << 1;
    obj.get_xy(x, y);
    cout << "After left shift X: " << x << ", Y: " << y << endl;
    obj = obj >> 1;
    obj.get_xy(x, y);
    cout << "After right shift X: " << x << ", Y: " << y << endl;

    return 0;
}


```

### Output:
![image](https://github.com/user-attachments/assets/81e9f1be-2990-45e7-af5f-32b87720a993)




## Problem No : 02 
Given the class

class three_d
{
int x, y, z;
public :
three_d (int i, int j, int k)
{
x = i; y = j; z = k;
}
three_d () { x=0; y=0; z=0; }
void get (int &i, int &j, int &k)
{
i = x; j = y; k = z;
}
};

overload the +, -, ++, and – operators for this class. (For the increment and decrement
operators, overload only the prefix form.)

## Code :

```
#include <iostream>
using namespace std;
class three_d {
    int x, y, z;
public:
    three_d(int i, int j, int k) {
        x = i;
        y = j;
        z = k;
    }

    three_d() {
        x = 0;
        y = 0;
        z = 0;
    }

    void get(int &i, int &j, int &k) {
        i = x;
        j = y;
        k = z;
    }

    three_d operator+(const three_d &ob) {
        three_d temp;
        temp.x = x + ob.x;
        temp.y = y + ob.y;
        temp.z = z + ob.z;
        return temp;
    }
    three_d operator-(const three_d &ob) {
        three_d temp;
        temp.x = x - ob.x;
        temp.y = y - ob.y;
        temp.z = z - ob.z;
        return temp;
    }

 three_d operator++() {
        ++x;
        ++y;
        ++z;
        return *this;
    }
    three_d operator--() {
        --x;
        --y;
        --z;
        return *this;
    }
   
};

int main() {
    three_d obj1(10, 20, 30), obj2(5, 15, 25), obj3;
    int x, y, z;

    obj3 = obj1 + obj2;
    obj3.get(x, y, z);
    cout << "After addition : x = " << x << ", y = " << y << ", z = " << z << endl;
    obj3 = obj1 - obj2;
    obj3.get(x, y, z);
    cout << "After subtraction : x = " << x << ", y = " << y << ", z = " << z << endl;
    ++obj1;
    obj1.get(x, y, z);
    cout << "After prefix increment : x = " << x << ", y = " << y << ", z = " << z << endl;
    --obj1;
    obj1.get(x, y, z);
    cout << "After prefix decrement : x = " << x << ", y = " << y << ", z = " << z << endl;

    return 0;
}


```

### Output:
![image](https://github.com/user-attachments/assets/bb25515f-b9ed-447a-987c-6a96d4828d17)



## Problem No : 03
Rewrite your answer to Question 2 so that it uses reference parameters  instead  of  value   
parameters to the operator functions. (Hint: You will need to use friend functions for the
increment and decrement operators.)
## Code :


```
#include <iostream>
using namespace std;

class three_d {
    int x, y, z;

public:
    three_d(int i, int j, int k) {
        x = i;
        y = j;
        z = k;
    }
    three_d() {
        x = 0;
        y = 0;
        z = 0;
    }

    void get(int &i, int &j, int &k) {
        i = x;
        j = y;
        k = z;
    }
    three_d& operator+(const three_d &ob) {
        x =x+ob.x;
        y =y+ ob.y;
        z =z+ ob.z;
        return *this;
    }
    three_d& operator-(const three_d &ob) {
        x =x+ ob.x;
        y =y+ ob.y;
        z =z+ ob.z;
        return *this;
    }
    friend three_d& operator++(three_d &o) {
        ++o.x;
        ++o.y;
        ++o.z;
        return o;
    }
    friend three_d& operator--(three_d &o) {
        --o.x;
        --o.y;
        --o.z;
        return o;
    }
};

int main() {
    three_d obj1(10, 20, 30), obj2(5, 15, 25), obj3;
    int x, y, z;
    obj1 + obj2;
    obj1.get(x, y, z);
    cout << "After addition : x = " << x << ", y = " << y << ", z = " << z << endl;
    obj1 - obj2;
    obj1.get(x, y, z);
    cout << "After subtraction : x = " << x << ", y = " << y << ", z = " << z << endl;
    ++obj1;
    obj1.get(x, y, z);
    cout << "After prefix increment : x = " << x << ", y = " << y << ", z = " << z << endl;
    --obj1;
    obj1.get(x, y, z);
    cout << "After prefix decrement : x = " << x << ", y = " << y << ", z = " << z << endl;

    return 0;
}


```

### Output:
![image](https://github.com/user-attachments/assets/5078e85b-6d26-4fbd-8e4b-9785ea0df622)

## Problem No : 04
How do friend operator functions differ from member operator functions?

### Answer :
Friend operator functions differ from member operator functions primarily in how they access class members and the types of operands they can handle. A member operator function is a function that belongs to a class and is called on an instance of that class, with the left-hand operand being the object itself (i.e., this pointer). In contrast, a friend operator function is defined outside the class but is granted access to the class’s private and protected members. It does not have a this pointer, so it can operate on multiple objects from different classes or types, making it more flexible for operations where the left-hand operand is not necessarily of the class type. This allows expressions like int + MyClass, which would not be possible with member operator functions. Essentially, friend functions provide broader applicability, while member functions are more intrinsic to the class.

## Problem No : 05
 Explain why you might need to overload the assignment operator
### Answer :
Overloading the assignment operator (operator=) is necessary when a class manages dynamic memory or other resources (like file handles or network connections) that require careful handling during object copying. By default, C++ provides a shallow copy for assignment, meaning it simply copies the pointer values rather than duplicating the actual content they point to. This can lead to issues like double deletion, memory leaks, or undefined behavior when multiple objects share the same resource. Overloading the assignment operator allows you to implement deep copying, where each object gets its own copy of the resource, ensuring proper memory management and avoiding resource conflicts. It's particularly important for classes with pointers, dynamic arrays, or any resource that needs explicit cleanup.

## Problem No : 06
Can operator=() be a friend function?
### Answer :
No, the assignment operator (operator=()) cannot be a friend function; it must be a member function. This is because the assignment operator modifies the internal state of the left-hand side object, which must already exist. Only member functions have direct access to an object's private and protected members, allowing the modification of the object's internal state. A friend function does not have the same privileges for modifying the left-hand side object in an assignment, which is why operator=() must be defined as a member function.
