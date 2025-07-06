--- ❤️ ---

# 🚀 _Day 187. Classes and Objects_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/classes-and-objects/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
using namespace std;

class Student {
private:
    string name;
    string branch;
public:
    Student(string n, string b) : name(n), branch(b) {}
    void printFunction() {
        cout << name << " " << branch << endl;
    }
};

int main() {
    // Create two Student objects
    Student stud1("Robin", "CSE");
    Student stud2("Rahul", "ECE");
    
    // Call printFunction for each student
    stud1.printFunction();
    stud2.printFunction();
    
    return 0;
}
```

## Code (Java)

```java
public class Student {
    private String name;
    private String branch;

    public Student(String name, String branch) {
        this.name = name;
        this.branch = branch;
    }

    public void printFunction() {
        System.out.println(name + " " + branch);
    }

    public static void main(String[] args) {
        // Create two Student objects
        Student stud1 = new Student("Robin", "CSE");
        Student stud2 = new Student("Rahul", "ECE");
        
        // Call printFunction for each student
        stud1.printFunction();
        stud2.printFunction();
    }
}
```

## Code (Python)

```python
class Student:
    def __init__(self, name, branch):
        self.name = name
        self.branch = branch
    def printfunction(self):
        print(self.name + " " + self.branch)

def main():
    # Create two Student objects
    stud1 = Student("Robin", "CSE")
    stud2 = Student("Rahul", "ECE")
    
    # Call printfunction for each student
    stud1.printfunction()
    stud2.printfunction()
    return 0

if __name__ == '__main__':
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
