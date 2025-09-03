--- ❤️ ---

# 🚀 _Day 246. Cpp Exception Handling_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/cpp-exception-handling/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b;
    cin >> a >> b;

    try {
        int result = division(a, b);  // function is already defined in hidden code
        cout << result;
    }
    catch (const char* msg) {
        cout << msg;
    }

    return 0;
}

```

## Code (Java)

```java
import java.util.Scanner;

public class Main {
    public static int division(int a, int b) throws Exception {
        if (b == 0) {
            throw new Exception("Division by zero condition!");
        }
        return a / b;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();

        try {
            int result = division(a, b);
            System.out.println(result);
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}

```

## Code (Python)

```python
def division(a, b):
    if b == 0:
        raise Exception("Division by zero condition!")
    return a // b   # integer division (like C++ / for ints)

try:
    a, b = map(int, input().split())
    result = division(a, b)
    print(result)
except Exception as e:
    print(e)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
