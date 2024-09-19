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
