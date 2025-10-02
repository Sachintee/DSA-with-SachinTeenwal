--- ❤️ ---

# 🚀 _Day 275. Recursion_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/recursion/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

int fibonacci(int n) {
    if (n == 0) return 0;
    if (n == 1) return 1;
    
    int a = 0, b = 1;
    for (int i = 2; i <= n; i++) {
        int temp = a + b;
        a = b;
        b = temp;
    }
    return b;
}

int main() {
    int A;
    cin >> A;
    cout << fibonacci(A) << endl;
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;

public class Main {
    public static int fibonacci(int n) {
        if (n == 0) return 0;
        if (n == 1) return 1;
        
        int a = 0, b = 1;
        for (int i = 2; i <= n; i++) {
            int temp = a + b;
            a = b;
            b = temp;
        }
        return b;
    }
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int A = scanner.nextInt();
        System.out.println(fibonacci(A));
        scanner.close();
    }
}
```

## Code (Python)

```python
def fibonacci(n):
    if n == 0:
        return 0
    if n == 1:
        return 1
    
    a, b = 0, 1
    for i in range(2, n + 1):
        a, b = b, a + b
    return b

A = int(input().strip())
print(fibonacci(A))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
