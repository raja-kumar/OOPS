# Polymorphism

C++ polymorphism means that a call to a member function will cause a different implementation to be executed depending on the type of object that invokes the function.
### Simply, polymorphism means that a single function can have a number of different implementations.

```
#include <iostream>
using namespace std;

class Enemy {
    protected: 
        int attackPower;
    public:
        void setAttackPower(int a){
            attackPower = a;
        }
};

class Ninja: public Enemy {
    public:
        void attack() {
            cout << "Ninja! - "<<attackPower<<endl;
        }
};

class Monster: public Enemy {
    public:
        void attack() {
            cout << "Monster! - "<<attackPower<<endl;
        }
};

int main() {
    Ninja n;
    Monster m;
    Enemy *e1 = &n;
    Enemy *e2 = &m;

    e1->setAttackPower(20);
    e2->setAttackPower(80);

    n.attack();
    m.attack();
}
```

output

```
Ninja! - 20
Monster! - 80
```
