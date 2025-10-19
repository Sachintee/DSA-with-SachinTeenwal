--- ❤️ ---

# 🚀 _Day 292. Exception Handling in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/exception-handling-in-c/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

void divide(int a, int b) {
    try {
        if (b == 0) throw 1;
        cout << a / b << endl;
    } catch (...) {
        cout << "Exception" << endl;
    }
}

int main() {
    int a, b;
    cin >> a >> b;
    divide(a, b);
    return 0;
}

```

## Code (Java)

```java
import java.util.Scanner;

public class Main {

    static void divide(int a, int b) {
        try {
            System.out.println(a / b);
        } catch (Exception e) {
            System.out.println("Exception");
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();
        divide(a, b);
    }
}

```

## Code (Python)

```python
def divide(a, b):
    try:
        print(a // b)
    except Exception:
        print("Exception")

a = int(input())
b = int(input())
divide(a, b)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
