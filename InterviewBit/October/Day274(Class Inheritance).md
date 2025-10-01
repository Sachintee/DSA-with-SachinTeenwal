--- ❤️ ---

# 🚀 _Day 274. Class Inheritance_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/class-inheritance/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
using namespace std;

class A {
public:
    string x;
    string y;
    
    A(string x, string y) {
        this->x = x;
        this->y = y;
    }
};

class B : public A {
public:
    string z;
    
    B(string x, string y, string z) : A(x, y) {
        this->z = z;
    }
    
    void printIB() {
        cout << "IB" << endl;
    }
};

int main() {
    string x, y, z;
    cin >> x >> y >> z;
    
    B b(x, y, z);
    
    cout << b.x << endl;
    cout << b.y << endl;
    cout << b.z << endl;
    b.printIB();
    
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;

class A {
    String x;
    String y;
    
    public A(String x, String y) {
        this.x = x;
        this.y = y;
    }
}

class B extends A {
    String z;
    
    public B(String x, String y, String z) {
        super(x, y);
        this.z = z;
    }
    
    public void printIB() {
        System.out.println("IB");
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        String x = scanner.nextLine();
        String y = scanner.nextLine();
        String z = scanner.nextLine();
        
        B b = new B(x, y, z);
        
        System.out.println(b.x);
        System.out.println(b.y);
        System.out.println(b.z);
        b.printIB();
        
        scanner.close();
    }
}
```

## Code (Python)

```python
class A:
    def __init__(self, x, y):
        self.x = x
        self.y = y

class B(A):
    def __init__(self, x, y, z):
        super().__init__(x, y)
        self.z = z
    
    def printIB(self):
        print("IB")

# Read input
x = input().strip()
y = input().strip()
z = input().strip()

# Create instance
b = B(x, y, z)

# Print properties and call method
print(b.x)
print(b.y)
print(b.z)
b.printIB()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
