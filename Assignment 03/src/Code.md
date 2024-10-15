## Code -1.1:
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
## Code -1.2:
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
## Code-1.3:
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
## Code-2.1:
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
## Code-2.5:
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
## Code-2.6:
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
## Code-3.6:
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
