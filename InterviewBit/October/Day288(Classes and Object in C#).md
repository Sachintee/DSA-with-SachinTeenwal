--- ❤️ ---

# 🚀 _Day 288. Classes and Object in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/classes-and-object-in-c/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
using namespace std;

class Student {
private:
    string name;
    int age;
    int roll;
    
public:
    void insert(string n, int a, int r) {
        name = n;
        age = a;
        roll = r;
    }
    
    void display() {
        cout << name << " " << age << " " << roll << endl;
    }
};
```

## Code (Java)

```java
public class Student {
    private String name;
    private int age;
    private int roll;
    
    public void insert(String name, int age, int roll) {
        this.name = name;
        this.age = age;
        this.roll = roll;
    }
    
    public void display() {
        System.out.println(name + " " + age + " " + roll);
    }
}
```

## Code (Python)

```python
class Student:
    def insert(self, name, age, roll):
        self.name = name
        self.age = age
        self.roll = roll
    
    def display(self):
        print(f"{self.name} {self.age} {self.roll}")
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
