## Pure Virtual Function

virtual functions can also have their own implementations in the base class.
However, in some situations you'd want to include a virtual function in a base class so that it may be redefined in a derived class to suit the objects of that class, but that there is no meaningful definition you could give for the function in the base class.
The virtual member functions without definition are known as **pure virtual functions**. They basically specify that the derived classes define that function on their own.
The syntax is to replace their definition by =0 (an equal sign and a zero):

```class Enemy {
 public:
  virtual void attack() = 0;
};
```

**The = 0 tells the compiler that the function has no body.**

A pure virtual function basically defines, that the derived classes will have that function defined on their own.
Every derived class inheriting from a class with a pure virtual function **must override** that function.

## Abstract Class

You cannot create objects of the base class with a pure virtual function. 

These classes are called abstract. They are classes that can only be used as base classes, and thus are allowed to have pure virtual functions.

You might think that an abstract base class is useless, but it isn't. It can be used to create pointers and take advantage of all its polymorphic abilities.

example

```
#include <iostream>
using namespace std;

class Enemy {
    public:
        virtual void attack() = 0;
};

class Ninja: public Enemy {
    public:
        void attack() {
            cout << "Ninja!"<<endl;
        }
};

class Monster: public Enemy {
    public:
        void attack() {
            cout << "Monster!"<<endl;
        }
};


int main()
{
    Ninja n;
    Monster m;
    Enemy *e1 = &n;
    Enemy *e2 = &m;

    e1->attack();
    e2->attack();

    return 0;
}
```

output
```
Ninja!
Monster!
```
