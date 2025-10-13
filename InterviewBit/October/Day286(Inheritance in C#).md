--- ❤️ ---

# 🚀 _Day 286. Inheritance in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/inheritance-in-c/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    int length = 0, width = 0;
    void SetLength(int l, int w) {
        length = l;
        width = w;
    }
};

class Rectangle : public Shape {
public:
    int GetArea() {
        return length * width;
    }
};
```

## Code (Java)

```java
class Shape {
    public int length = 0, width = 0;
    public void SetLength(int l, int w) {
        length = l;
        width = w;
    }
}

class Rectangle extends Shape {
    public int GetArea() {
        return length * width;
    }
}
```

## Code (Python)

```python
class Shape:
    def __init__(self):
        self.length = 0
        self.width = 0
    
    def SetLength(self, l, w):
        self.length = l
        self.width = w

class Rectangle(Shape):
    def GetArea(self):
        return self.length * self.width
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
