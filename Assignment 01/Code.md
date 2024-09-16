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
