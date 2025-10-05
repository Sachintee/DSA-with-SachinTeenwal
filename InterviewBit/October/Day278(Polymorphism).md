--- ❤️ ---

# 🚀 _Day 278. Polymorphism_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/js-polymorphism/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    virtual int area() {
        return 0;
    }
    
    void print() {
        cout << "This is a shape." << endl;
    }
};

class Square : public Shape {
private:
    int s;
public:
    Square(int s) {
        this->s = s;
    }
    
    int area() override {
        return s * s;
    }
};

class Rectangle : public Shape {
private:
    int l, b;
public:
    Rectangle(int l, int b) {
        this->l = l;
        this->b = b;
    }
    
    int area() override {
        return l * b;
    }
};

// Testing code
int main() {
    Shape shape;
    Square square(10);
    Rectangle rectangle(20, 4);
    
    cout << shape.area() << endl;    // Output: 0
    cout << square.area() << endl;   // Output: 100
    cout << rectangle.area() << endl; // Output: 80
    
    return 0;
}
```

## Code (Java)

```java
class Shape {
    public int area() {
        return 0;
    }
    
    public void print() {
        System.out.println("This is a shape.");
    }
}

class Square extends Shape {
    private int s;
    
    public Square(int s) {
        this.s = s;
    }
    
    @Override
    public int area() {
        return s * s;
    }
}

class Rectangle extends Shape {
    private int l, b;
    
    public Rectangle(int l, int b) {
        this.l = l;
        this.b = b;
    }
    
    @Override
    public int area() {
        return l * b;
    }
}

// Testing class
public class Main {
    public static void main(String[] args) {
        Shape shape = new Shape();
        Square square = new Square(10);
        Rectangle rectangle = new Rectangle(20, 4);
        
        System.out.println(shape.area());    // Output: 0
        System.out.println(square.area());   // Output: 100
        System.out.println(rectangle.area()); // Output: 80
    }
}
```

## Code (Python)

```python
class Shape:
    def area(self):
        return 0
    
    def print(self):
        print("This is a shape.")

class Square(Shape):
    def __init__(self, s):
        self.s = s
    
    def area(self):
        return self.s * self.s

class Rectangle(Shape):
    def __init__(self, l, b):
        self.l = l
        self.b = b
    
    def area(self):
        return self.l * self.b

# Testing code
if __name__ == "__main__":
    shape = Shape()
    square = Square(10)
    rectangle = Rectangle(20, 4)
    
    print(shape.area())    # Output: 0
    print(square.area())   # Output: 100
    print(rectangle.area()) # Output: 80
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
