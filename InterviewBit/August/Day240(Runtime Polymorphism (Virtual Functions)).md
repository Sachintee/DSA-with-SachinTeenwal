--- ❤️ ---

# 🚀 _Day 240. Runtime Polymorphism (Virtual Functions)_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/runtime-polymorphism-virtual-functions/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include<iostream>
using namespace std;

// Animal class
class Animal {
protected:
    int age;
public:
    Animal(int a) : age(a) {}
    virtual void Eat() {
        cout << "Animal eats food" << endl;
    }
    virtual int get_Age() {
        return age;
    }
};

// Dog class
class Dog : public Animal {
public:
    Dog(int a) : Animal(a) {}
    void Eat() override {
        cout << "Dog eats meat" << endl;
    }
    int get_Age() override {
        return age;
    }
};

// Cat class
class Cat : public Animal {
public:
    Cat(int a) : Animal(a) {}
    void Eat() override {
        cout << "Cat eats meat" << endl;
    }
    int get_Age() override {
        return age;
    }
};

/*
int main()  {
   Animal *a;
   Dog dg(8); //making object of child class Dog
   Cat ct(3); //making object of child class Cat
   
   a = &dg;
   a->Eat();
   cout << "Dog's age is: "<<a->get_Age()<<endl;
   a= &ct;
   a->Eat();
   cout << "Cat's age is: "<<a->get_Age()<<endl;
   return 0;
}
*/
```

## Code (Java)

```java
class Animal {
    protected int age;
    
    public Animal(int age) {
        this.age = age;
    }
    
    public void eat() {
        System.out.println("Animal eats food");
    }
    
    public int getAge() {
        return age;
    }
}

class Dog extends Animal {
    public Dog(int age) {
        super(age);
    }
    
    @Override
    public void eat() {
        System.out.println("Dog eats meat");
    }
    
    @Override
    public int getAge() {
        return age;
    }
}

class Cat extends Animal {
    public Cat(int age) {
        super(age);
    }
    
    @Override
    public void eat() {
        System.out.println("Cat eats meat");
    }
    
    @Override
    public int getAge() {
        return age;
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a;
        Dog dg = new Dog(8);
        Cat ct = new Cat(3);
        
        a = dg;
        a.eat();
        System.out.println("Dog's age is: " + a.getAge());
        
        a = ct;
        a.eat();
        System.out.println("Cat's age is: " + a.getAge());
    }
}
```

## Code (Python3)

```python
class Animal:
    def __init__(self, age):
        self._age = age
    
    def eat(self):
        print("Animal eats food")
    
    def get_age(self):
        return self._age

class Dog(Animal):
    def __init__(self, age):
        super().__init__(age)
    
    def eat(self):
        print("Dog eats meat")
    
    def get_age(self):
        return self._age

class Cat(Animal):
    def __init__(self, age):
        super().__init__(age)
    
    def eat(self):
        print("Cat eats meat")
    
    def get_age(self):
        return self._age

# Main function
if __name__ == "__main__":
    dg = Dog(8)
    ct = Cat(3)
    
    animals = [dg, ct]
    
    for animal in animals:
        animal.eat()
        if isinstance(animal, Dog):
            print(f"Dog's age is: {animal.get_age()}")
        elif isinstance(animal, Cat):
            print(f"Cat's age is: {animal.get_age()}")
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
