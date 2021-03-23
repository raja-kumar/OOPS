## Inheritance
When inheriting classes, the base class' constructor and destructor are not inherited.
However, they are being called when an object of the derived class is created or deleted.

#### the base class' constructor is called first, and the derived class' constructor is called next.
#### When the object is destroyed, the derived class's destructor is called, and then the base class' destructor is called

```
#include <iostream>
using namespace std;

class Mother {
    public:
        Mother() 
        {
            cout <<"Mother ctor"<<endl;
        }
        ~Mother()
        {
            cout <<"Mother dtor"<<endl;
        }
};

class Daughter: public Mother {
    public:
        Daughter()
        {
            cout <<"Daughter ctor"<<endl;
        }
        ~Daughter()
        {
            cout <<"Daughter dtor"<<endl;
        }
};

int main() {
    Daughter m;
}
```

Output

```
Mother ctor
Daughter ctor
Daughter dtor
Mother dtor
```
