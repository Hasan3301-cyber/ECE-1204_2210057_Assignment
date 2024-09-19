# Assignment No: 01
# Date of Submission :16-09-2024
# Title : Find out the error in code with reason and Fix it

## Problem No : 01 (CLASS & OBJECT)
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




## Problem No : 02 (CLASS & OBJECT)
## Code with Error:
![error 2](https://github.com/user-attachments/assets/5f4f760f-7c63-4beb-a723-fb40f8c44289)

## Discussion :
In this code we call the data field with class name not with object so that the error occure because class is just a template it does not store data .So to overcome the error we have to call attribute with object
## Code with No Error:

```
#include <iostream>
#include <string>
class MyClass {
  public:
    int myNum;
    std::string myString;
};
int main() {
  MyClass myObj;
  myObj.myNum = 15;
  myObj.myString = "Some text";
  std::cout << myObj.myNum << "\n";
  std::cout << myObj.myString;
  return 0;
}


```

### Output:
![output 2](https://github.com/user-attachments/assets/22b7ca26-aae8-4c9c-9d2f-a98965ba7324)




## Problem No : 03 (ACCESS SPECIFIER)
## Code with Error:
![error 3](https://github.com/user-attachments/assets/0935578c-e300-4d8f-bb09-287fe346c890)

## Discussion :
y is not allowed because y is private and cannot be accessed directly from outside the class. This will result in a compilation error.to solve this error we have to use public set and get function
## Code with No Error:

```
#include <iostream>
using namespace std;
class MyClass {
  public:
    int x;
    void setY(int value) {
        y = value;}
    int getY() const {
        return y;
    }
  private:
    int y;
};
int main() {
  MyClass myObj;
  myObj.x = 25;
  myObj.setY(50);
  cout << myObj.getY();
  return 0;
}
```

### Output:
![o3](https://github.com/user-attachments/assets/4719108c-8955-4fbe-9df0-5c06ce84f740)




## Problem No : 04 (FRIEND FUNCTION)
## Code with Error:
![image](https://github.com/user-attachments/assets/8fb9c69f-75e3-4c8a-a052-9d14788439e0)
## Discussion :
In above code the error occur because of missing declaration of Friend Function inside class.The printWidth function doesn't have access to private or protected members of box object it works like normal function
## Code with No Error:

```
#include <iostream>
using namespace std;
class Box {
   double width;
   public:
      void setWidth(double wid);
      friend void printWidth(Box box);
};
void Box::setWidth(double wid) {
   width = wid;
}
void printWidth(Box box) {
   cout << "Width of box : " << box.width << endl;
}
int main() {
   Box box;
   box.setWidth(10.0);
   printWidth(box);
   return 0;
}
```

### Output:
![o4](https://github.com/user-attachments/assets/a69dc1eb-3277-465a-8c69-7d7169232ada)




## Problem No : 05 (FRIEND FUNCTION)
## Code with Error:
![error 5](https://github.com/user-attachments/assets/200068bc-3d1c-45c8-b126-9e4b5188f9cc)

## Discussion :
Object does not pass to friend function in this code.In friend function we need to pass object of that specific function because friend function need access to private or protected data of an object as friend function not a member function ,they don't have an implicit object
## Code with No Error:

```
#include <iostream>
using namespace std;
class Box {
   double width;
   public:
      void setWidth(double wid);
      friend void printWidth(Box box);
};
void Box::setWidth(double wid) {
   width = wid;
}
void printWidth(Box box) {
   cout << "Width of box : " << box.width << endl;
}
int main() {
   Box box;
   box.setWidth(10.0);
   printWidth(box);
   return 0;
}
```

### Output:

![output 5](https://github.com/user-attachments/assets/9ce85f69-be5b-400d-8b98-c1f6ab1c525c)



