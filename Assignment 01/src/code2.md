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
