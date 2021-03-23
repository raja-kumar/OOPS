## Type of Inheritance


Access specifiers are also used to specify the type of inheritance.

Remember, we used public to inherit the Daughter class:
```
class Daughter: public Mother
```
private and protected access specifiers can also be used here.

Public Inheritance: public members of the base class become public members of the derived class and protected members of the base class become protected members of the derived class. A base class's private members are never accessible directly from a derived class, but can be accessed through calls to the public and protected members of the base class.

Protected Inheritance: public and protected members of the base class become protected members of the derived class.

Private Inheritance: public and protected members of the base class become private members of the derived class.
