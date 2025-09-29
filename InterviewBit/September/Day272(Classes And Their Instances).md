--- ❤️ ---

# 🚀 _Day 272. Classes And Their Instances_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/classes-and-their-instances/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
using namespace std;

class Employee {
private:
    string name;
    string position;
    string skill;
    
public:
    // Constructor
    Employee(string n, string p, string s) {
        name = n;
        position = p;
        skill = s;
    }
    
    // Getter methods (optional but good practice)
    string getName() { return name; }
    string getPosition() { return position; }
    string getSkill() { return skill; }
};

int main() {
    string defaultName, defaultPosition, defaultSkill;
    
    cin >> defaultName;
    cin >> defaultPosition;
    cin >> defaultSkill;
    
    Employee emp(defaultName, defaultPosition, defaultSkill);
    
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;

class Employee {
    private String name;
    private String position;
    private String skill;
    
    // Constructor
    public Employee(String name, String position, String skill) {
        this.name = name;
        this.position = position;
        this.skill = skill;
    }
    
    // Getter methods (optional but good practice)
    public String getName() {
        return name;
    }
    
    public String getPosition() {
        return position;
    }
    
    public String getSkill() {
        return skill;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        String defaultName = scanner.nextLine();
        String defaultPosition = scanner.nextLine();
        String defaultSkill = scanner.nextLine();
        
        Employee emp = new Employee(defaultName, defaultPosition, defaultSkill);
        
        scanner.close();
    }
}
```

## Code (Python)

```python
class Employee:
    def __init__(self, name, position, skill):
        self.name = name
        self.position = position
        self.skill = skill

# Reading input
defaultName = input().strip()
defaultPosition = input().strip()
defaultSkill = input().strip()

# Creating instance
emp = Employee(defaultName, defaultPosition, defaultSkill)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
