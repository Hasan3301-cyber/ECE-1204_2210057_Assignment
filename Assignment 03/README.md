# Assignment No: 03
# Date of Submission :15-10-2024
# Title : Skill check on the topics of operator overloading, inheritance, and virtual functions.
## 1. Operator Overloading
## Problem No : 01 
Overload the >> and << shift operator relative to the coord class so that the following
types of operations are allowed:

ob << integer 
        
ob >> integer

Make sure your operations shift the x and y values by the amount specified.
## Answer:
### Code :

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
```
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
```
overload the +, -, ++, and – operators for this class. (For the increment and decrement
operators, overload only the prefix form.)
## Answer:
### Code :

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
## Answer:
### Code :


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
# 2. Inheritance

## Problem No : 01
Create a generic base class called building that stores the number of floors a building has,
the number of rooms, and its total square footage. Create derived class called house that
inherits building and also stores the number of bedrooms and the number of bathrooms.
Next, create a derived class called office that inherits building and also stores the number
of fire extinguishers and the number of telephones.
### Answer:
## Code :

```
#include <iostream>
using namespace std;
class building
{
protected:
    int floor;
    int room;
    double sqr;

public:
    building(int x, int y, double z)
    {
        floor = x;
        room = y;
        sqr = z;
    }

    void display()
    {
        cout << "Floor: " << floor << "\nRooms: " << room << "\nSquare Footage: " << sqr << endl;
    }
};

class house : public building
{
private:
    int bedroom;
    int bathroom;

public:
    house(int x, int y, double z, int a, int b)
        : building(x, y, z)
    {

        bedroom=a;
        bathroom=b;
    }

    void display()
    {

        cout << "Floors: " << floor << "\nRooms: " << room << "\nSquare Footage: " << sqr << endl;
        cout << "Bedroom: " << bedroom << "\nBathroom: " << bathroom << endl;
    }
};

class office : public building
{
private:
    int extinguisher ;
    int telephone;

public:
    office(int x, int y, double z, int a, int b)
        : building(x, y, z)
    {
        extinguisher=a;
        telephone=b;
    }

    void display()
    {
        building::display();
        cout << "Fire Extinguisher: " << extinguisher << "\nTelephones: " << telephone << endl;
    }
};

int main()
{

    house a(2, 5, 2500.0, 3, 2);
    cout << "House Info: " << endl;
    a.display();
    cout << endl;

    office b(5, 20, 10000.0, 15, 50);
    cout << "Office Info: " << endl;
    b.display();

    return 0;
}


```

### Output:
![image](https://github.com/user-attachments/assets/f575d429-aeab-43be-be61-a043d8d318e9)


## Problem No : 02
When a base class is inherited as public by the derived class, what happens to its public
members? What happens to its private members? If the base is inherited as private by
the derived class, what happens to its public and private members?
## Answer :

### For Public Inheritance:
#### Public Members of the base class: 
Remain public in the derived class. They can be accessed by the derived class and by external code that uses objects of the derived class.
#### Private Members of the base class: 
Remain private and cannot be accessed directly by the derived class or external code. They can only be accessed via public or protected methods provided by the base class.
### For Private Inheritance:
#### Public Members of the base class: 
Become private in the derived class. They can still be accessed by the derived class, but not by external code(Like from main class).
#### Private Members of the base class: 
Remain private and cannot be accessed by the derived class or external code. Access is possible only through public or protected methods of the base class.



## Problem No : 03
Explain what protected means. (Be sure to explain what it means both when referring
to members of a class and when it is used as an inheritance access specifier.)
## Answer :
### Protected Members of a Class:
When a class member (either a variable or a function) is declared as protected, it is accessible only within the class itself and any of its derived (child) classes. This means that while the member remains hidden from outside access like private members, derived classes can still directly use or modify it. This gives derived classes controlled access to important data or functionality without exposing those details to other parts of the program. For example, if a base class has a protected member, a derived class can access it to enhance or extend its behavior while keeping the internal details hidden from external users.
### Protected as an Inheritance Access Specifier:
When protected is used as an inheritance specifier (i.e., class Derived : protected Base), it determines how the base class's members are inherited by the derived class. In this case, all public and protected members of the base class become protected in the derived class, meaning they can be accessed within the derived class and its children but are not accessible from outside. This form of inheritance is useful **when you want** to allow a derived class to utilize the base class’s functionality internally while keeping those details hidden from other parts of the program. Private members of the base class, however, remain inaccessible to the derived class, regardless of the inheritance specifier.

## Problem No : 04
When one class inherits another, when are the classes’ constructors called? When are
their destructors called?
## Answer :
When one class inherits another, the constructors and destructors of both classes are called in a specific order. First, when an object of the derived class is created, the constructor of the base class is called before the constructor of the derived class. This happens because the derived class depends on the proper initialization of the base class before it can be constructed. The base class's constructor is responsible for setting up any base-level attributes or behaviors that the derived class may build upon.
Similarly, when an object of the derived class is destroyed, the destructors are called in the reverse order: the destructor of the derived class is called first, followed by the destructor of the base class. This ensures that any resources or attributes specific to the derived class are cleaned up before the base class's cleanup occurs. Thus, constructors are called in a base-to-derived order, while destructors are called in a derived-to-base order.

## Problem No : 05 
Given this skeleton, fill in the details as indicated in the comments:
```
# include <iostream >
using namespace std;
class planet
{
protected :
double distance ; // miles from the sun
int revolve ; // in days
public :
planet ( double d, int r) { distance = d; revolve = r; }
};
class earth : public planet
{
double circumference ; // circumference of orbit
public :
/*
Create earth ( double d, int r). Have it pass the
distance and days of revolution back to planet .
Have it compute the circumference of the orbit .
( Hint : circumference = 2r *3.1416.)
*/
/*
Create a function called show () that displays the
information .
*/
};
int main ()
{
earth ob (93000000 , 365) ;
ob. show ();
return 0;
}
```
## Answer:
### Code :

```
#include <iostream>
using namespace std;
class planet
{
protected:
    double distance;
    int revolve;

public:
    planet(double d, int r)
    {
        distance = d;
        revolve = r;
    }
};

class earth : public planet
{
    double cir;

public:
    earth(double d, int r) : planet(d, r)
    {
        cir = 2 * 3.1416 * distance;
    }
    void show()
    {
        cout << "Distance from the sun: " << distance << " miles" << endl;
        cout << "Revolution period: " << revolve << " days" << endl;
        cout << "Circumference of orbit: " << cir << endl;
    }
};

int main()
{
    earth ob(9300000, 365);
    ob.show();

    return 0;
}



```

### Output:
![Output 5](https://github.com/user-attachments/assets/a8136454-9348-45f6-b99e-028617ca5c88)




## Problem No : 06
Fix the following program
```
/*
A variation on the vehicle hierarchy . But
this program contains an error . Fix it. Hind :
try compiling it as is and observe the error
messages .
*/
# include <iostream >
using namespace std;
// A base class for various types of vehicles .
class vehicle
{
int num_wheels ;
int range ;
public :
vehicle (int w, int r)
{
num_wheels = w;
range = r;
}
void showv ()
{
cout << " Wheels : " << num_wheels << ’\n’;
cout << " Range : " << range << ’\n’;

}
};
enum motor {gas , electric , diesel };
class motorized : public vehicle
{
enum motor mtr ;
public :
motorized ( enum motor m, int w, int r) : vehicle (w, r)
{
mtr = m;
}
void showm ()
{
cout << " Motor : ";
switch (mtr )
{
case gas : cout << "Gas \n";
break ;
case electric : cout << " Electric \n";
break ;
case diesel : cout << " Diesel \n";
break ;
}
}
};
class road_use : public vehicle
{
int passengers ;
public :
road_use (int p, int w, int r) : vehicle (w, r)
{
passengers = p;
}
void showr ()
{
cout << " Passengers : " << passengers << ’\n’;
}
};
enum steering { power , rack_pinion , manual };
class car : public motorized , public road_use
{
enum steering strng ;
public :
car ( enum steering s, enum motor m, int w, int r, int p) :
road_use (p, w, r), motorized (m, w, r), vehicle (w, r)
{
strng = s;
}
void show ()
{
showv ();
showr ();
showm ();
cout << " Steering : ";
switch ( strng )
{
case power : cout << " Power \n";
break ;
case rack_pinion : cout << " Rack and Pinion \n";
break ;
case manual : cout << " Manual \n";
break ;
}
}
};
int main ()
{
car c(power , gas , 4 , 500 , 5);
c. show ();
return 0;
}
```
## Answer:
### Code :

```
#include <iostream>
using namespace std;
class vehicle {
protected:
    int num_wheels;
    int range;

public:
    vehicle(int w, int r) {
        num_wheels = w;
        range = r;
    }
    void showv() {
        cout << "Wheels: " << num_wheels << '\n';
        cout << "Range: " << range << '\n';
    }
};

enum motor { gas, electric, diesel };

class motorized : virtual public vehicle {
    enum motor mtr;

public:
    motorized(enum motor m, int w, int r) : vehicle(w, r) {
        mtr = m;
    }

    void showm() {
        cout << "Motor: ";
        switch (mtr) {
            case gas: cout << "Gas\n"; break;
            case electric: cout << "Electric\n"; break;
            case diesel: cout << "Diesel\n"; break;
        }
    }
};

class road_use : virtual public vehicle {
    int passengers;

public:
    road_use(int p, int w, int r) : vehicle(w, r) {
        passengers = p;
    }

    void showr() {
        cout << "Passengers: " << passengers << '\n';
    }
};

enum steering { power, rack_pinion, manual };

class car : public motorized, public road_use {
    enum steering strng;

public:
    car(enum steering s, enum motor m, int w, int r, int p)
        : vehicle(w, r), motorized(m, w, r), road_use(p, w, r) {
        strng = s;
    }

    void show() {
        showv(); 
        showr();  
        showm();  
        cout << "Steering: ";
        switch (strng) {
            case power: cout << "Power\n"; break;
            case rack_pinion: cout << "Rack and Pinion\n"; break;
            case manual: cout << "Manual\n"; break;
        }
    }
};

int main() {
    car c(power, gas, 4, 500, 5);
    c.show();
    return 0;
}

```

### Output:
![image](https://github.com/user-attachments/assets/2d04002f-129c-4871-87fe-f7348047bd96)

### Discussion:
The issue in this code is caused by multiple inheritance. Both the motorized and road_use classes inherit from vehicle, leading to ambiguity when the derived class car tries to access the members of vehicle. Specifically, this causes the showv() method in car to be ambiguous. To resolve this issue, you can use virtual inheritance to ensure that only one instance of the vehicle class is shared by both motorized and road_use when inherited by car.

# Virtual Function
## Problem No : 01
What is a virtual function?
## Answer :
A virtual function is a function in a base class that is declared using the keyword virtual and is intended to be overridden in derived classes. When a function is marked as virtual, it allows the derived class to provide its own implementation of that function, enabling polymorphism

## Problem No : 02
What types of functions cannot be made virtual?
## Answer :
Constructors, static functions, friend functions, and non-member functions cannot be made virtual
#### Constructors:
Reason: Constructors cannot be virtual because they are responsible for creating the object, including setting up the virtual table (vtable). Virtual dispatch requires an already constructed object, but the object is not fully constructed during the constructor call, making it impossible to use virtual mechanisms.
#### Static Functions:
Reason: Static functions belong to the class, not to any specific object instance. Since virtual functions rely on the runtime type of an object (via the vtable), and static functions do not operate on instances, they cannot be made virtual.
#### Friend Functions:
Reason: Friend functions are not members of the class but external functions granted access to private members. Since they do not belong to the class hierarchy, they cannot participate in virtual dispatch, which is only applicable to member functions.
#### Non-Member Functions:
Reason: Non-member functions are independent of any class and are not part of a class hierarchy. Virtual functions depend on class inheritance and object instances, which non-member functions lack, thus preventing them from being virtual.



## Problem No : 03
How does a virtual function help achieve run-time polymorphism? Be specific.
## Answer :
Run-time polymorphism, also known as dynamic binding, is a feature in object-oriented programming that allows the system to determine which function to call at runtime based on the actual object type. Virtual functions play a crucial role in achieving this.
### Mechanism:
Virtual Table (vtable):
The compiler creates a vtable for classes with virtual functions. This table contains pointers to the virtual functions, enabling the program to decide at runtime which function to call based on the actual object type.

Dynamic Dispatch:
Each object of a class with virtual functions contains a hidden pointer (often called vptr) to its class's vtable. When a virtual function is called, the program looks up the function pointer in the vtable associated with the object, ensuring that the correct function is executed.


## Problem No : 04
What is a pure virtual function?
## Answer :
A pure virtual function in C++ is a function that has no implementation in the base class and must be overridden by any derived class that inherits from it. It is used to define an abstract class, which cannot be instantiated on its own but serves as a blueprint for derived classes.:
#### Syntex:
```
class Base {
public:
    virtual void display() = 0; 
};
```
## Problem No : 05
What is an abstract class? What is a polymorphic class?
## Answer :
### Abstract Class
An abstract class in C++ is a class that cannot be instantiated directly and is designed to be inherited by other classes. It typically contains at least one pure virtual function, which forces the derived classes to implement the pure virtual functions. Abstract classes are used to provide a common interface for a group of related classes while leaving the implementation details to the derived classes.
### Polymorphic Class
A polymorphic class in C++ is any class that contains at least one virtual function. Polymorphic classes enable runtime polymorphism, where the function that is called is determined at runtime based on the actual object type, rather than the type of reference or pointer.

## Problem No : 06
Is the following fragment correct? If not, why not?
```
class base
{
public :
virtual int (int a) = 0;
// ...
};
class derived : public base
{
public :
int f(int a, int b) { return a*b; }
// ...
}:
```
## Answer:
### Correct Code :
```
class base
{
public:
    virtual int f(int a) = 0;
};

class derived : public base
{
public:
    int f(int a) override
    {
        return a;
    }
};


```

### Discussion:
1.	A pure virtual function must have a name, but in this case, the function lacks a name. The correct syntax should include a function name, such as f.
2.	The pure virtual function and overridden function in derived class must have same and number of same parameters.But on this code have not same parameter.
3.	The class definition is terminated with : instead of a semicolon (;). The correct syntax for class termination is a semicolon.

## Problem No : 07
Is the virtual quality inherited?
## Answer :
The virtual quality of a member function is indeed inherited by derived classes. This means that if a base class declares a member function as virtual, any derived class that overrides that function will also have it considered as virtual, allowing for polymorphism.
