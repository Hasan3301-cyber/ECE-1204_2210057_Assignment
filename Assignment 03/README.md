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
## Code with Error:
![error1](https://github.com/user-attachments/assets/831c8e9f-2f4b-4d8f-9d00-c58de5d5773e)

## Discussion :
In this code error occurs due to miss Namespace Prefix std.Without the std:: prefix or a using namespace std; directive, the compiler will not recognize string and cout.
## Code with No Error:

```
#include <iostream>
#include <string>
using namespace std;
class MyClass {
  public:
    int myNum;
    string myString;
};
int main() {
  MyClass myObj;
  myObj.myNum = 15;
  myObj.myString = "Some text";
  cout << myObj.myNum << "\n";
  cout << myObj.myString;
  return 0;
}



```

### Output:
![Output 1](https://github.com/user-attachments/assets/e3194c8b-946b-41df-b3a7-5c7851166dc4)




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
    three_d operator-(const three_d &obj) {
        three_d temp;
        temp.x = x - obj.x;
        temp.y = y - obj.y;
        temp.z = z - obj.z;
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







