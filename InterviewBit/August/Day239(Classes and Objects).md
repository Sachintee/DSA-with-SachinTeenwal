--- ❤️ ---

# 🚀 _Day 239. Classes and Objects_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/classes-and-objects-cpp/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Student {
    string name;
    int age;
    int rollno;
public:
    void set_variable(string n, int a, int r) {
        name = n;
        age = a;
        rollno = r;
    }

    void print_variable() {
        cout << name << endl;
        cout << age << endl;
        cout << rollno << endl;
    }
};

```

## Code (Java)

```java
class Student {
    private String name;
    private int age;
    private int rollno;

    void set_variable(String n, int a, int r) {
        name = n;
        age = a;
        rollno = r;
    }

    void print_variable() {
        System.out.println(name);
        System.out.println(age);
        System.out.println(rollno);
    }
}

public class Main {
    public static void main(String[] args) {
        Student obj1 = new Student();
        obj1.set_variable("Robin", 15, 10);

        Student obj2 = new Student();
        obj2.set_variable("Rahul", 20, 14);

        obj1.print_variable();
        obj2.print_variable();
    }
}

```

## Code (Python3)

```python
class Student:
    def __init__(self):
        self.__name = ""
        self.__age = 0
        self.__rollno = 0

    def set_variable(self, name, age, rollno):
        self.__name = name
        self.__age = age
        self.__rollno = rollno

    def print_variable(self):
        print(self.__name)
        print(self.__age)
        print(self.__rollno)


# Example usage
obj1 = Student()
obj1.set_variable("Robin", 15, 10)

obj2 = Student()
obj2.set_variable("Rahul", 20, 14)

obj1.print_variable()
obj2.print_variable()

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
