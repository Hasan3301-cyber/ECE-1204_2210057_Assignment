## Problem No : 01 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/a7aa5b36-9706-461e-b279-56cc27f20f9e)
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
![image](https://github.com/user-attachments/assets/417f0303-fbc8-4423-9639-59772d1c68ea)


## Problem No : 02 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/900c74c2-891b-40bb-9a13-6e04ef28470c)
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
![image](https://github.com/user-attachments/assets/001c0dc4-4935-4112-ab5f-35ca86657055)


## Problem No : 03 (ACCESS SPECIFIER)
## Code with Error:
![image](https://github.com/user-attachments/assets/fd68f019-0926-450e-b0f9-e02665e949bd)
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
![image](https://github.com/user-attachments/assets/4c1a1b17-2965-492a-aaa6-2f356722ac39)


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
![image](https://github.com/user-attachments/assets/eae0c88a-f5c6-4575-9cf8-7fe764a28bb3)


## Problem No : 05 (FRIEND FUNCTION)
## Code with Error:
![image](https://github.com/user-attachments/assets/9fa0e5b1-94b0-4ca1-a6d4-7a386920699b)
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

![image](https://github.com/user-attachments/assets/ecde9d78-a916-4de5-9a32-573ef66c1f93)


## Problem No : 06 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
## Discussion :
## Code with No Error:

```


```

### Output:

![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)

## Problem No : 07 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
## Discussion :
## Code with No Error:

```


```

### Output:

![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)

## Problem No : 08 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
## Discussion :
## Code with No Error:

```


```

### Output:

![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)

## Problem No : 09 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
## Discussion :
## Code with No Error:

```


```

### Output:

![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)

## Problem No : 10 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
## Discussion :
## Code with No Error:

```


```

### Output:

![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)

## Problem No : 11 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
## Discussion :
## Code with No Error:

```


```

### Output:

![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)

## Problem No : 12 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
## Discussion :
## Code with No Error:

```


```

### Output:

![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)

## Problem No : 01 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
## Discussion :
## Code with No Error:

```


```

### Output:

![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)

## Problem No : 01 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
## Discussion :
## Code with No Error:

```


```

### Output:

![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)

## Problem No : 01 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
## Discussion :
## Code with No Error:

```


```

### Output:

![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)

## Problem No : 01 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
## Discussion :
## Code with No Error:

```


```

### Output:

![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
