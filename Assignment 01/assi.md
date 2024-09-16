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


## Problem No : 04 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
## Discussion :
## Code with No Error:

```


```

### Output:

![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)

## Problem No : 05 (CLASS & OBJECT)
## Code with Error:
![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)
## Discussion :
## Code with No Error:

```


```

### Output:

![image](https://github.com/user-attachments/assets/210707f8-eed5-4417-b7a6-3ecd9db80da5)

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
