

Title: Polymorphism
---

## How to do the Polymorphism

We will be looking at the code below this. We will be breaking it down a few lines at a time and assuming that you know what are iostream, class, functions and all that stuff.


```cpp
#include <iostream>

class Item{
  protected:
    int recover = 0;

  public:
    void setItem(int a){
        recover = a;
    }
};

class Potion : public Item{
  public:
    int potionF()
    {
      return recover;
    }
};

int main()
{
  Potion potion;
  Item *itemPotion = &potion;
  itemPotion->setItem(15);
  
 std::cout <<  potion.potionF() << std::endl;
  
  return 0;
}
```

---

## class: Item

let's look at what the first class is doing. What the first class is doing is that we first intialized "recover" and placed it under protected which can be accessed by a child class. Then what the function can do is set a number to recover. 

* For more information on **"class"** click on the link below.

**Note-to-self: add a link to class here**

```cpp
class Item{
  protected:
    int recover = 0;

  public:
    void setItem(int a){
        recover = a;
    }
};
  
```

## class potion

In the class potion the function called **potionF**  returns the value of **recover** beacause the function is able to access the protected class from the parent class **Item** and if it were private then the child class **Potion** would not be able to return the value of **recover** and instead it will return an error.

```cpp
  class Potion : public Item{
  public:
    int potionF()
    {
      return recover;
    }
};
```

## int main function

```cpp
int main()
{
// we first intialize it
  Potion potion;
  Item *itemPotion = &potion; // we the point the address of potion so we can set a value for potion
  
  //then we set the value here
  itemPotion->setItem(15);
  
 std::cout <<  potion.potionF() << std::endl;// then we use potion to access it's own function
 
 //output: 15
  
  return 0;
}
```

This is how you do the Polymorphism in C++

**Note:If you want a child class to access a variable from a ***"parent"*** class use protected instead of private**

