--- ❤️ ---

# 🚀 _Day 279. Operators in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/operators-in-c/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b;
    cin >> a >> b;
    
    int add = a + b;
    int sub = a - b;
    int multi = a * b;
    
    int div;
    if (b != 0) {
        div = a / b;
    } else {
        div = 0; // Handle division by zero
    }
    
    cout << add << endl << sub << endl << multi << endl << div << endl;
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int a = scanner.nextInt();
        int b = scanner.nextInt();
        
        int add = a + b;
        int sub = a - b;
        int multi = a * b;
        int div = (b != 0) ? a / b : 0;
        
        System.out.println(add);
        System.out.println(sub);
        System.out.println(multi);
        System.out.println(div);
        
        scanner.close();
    }
}
```

## Code (Python)

```python
a = int(input())
b = int(input())

add = a + b
sub = a - b
multi = a * b
div = a // b if b != 0 else 0

print(add)
print(sub)
print(multi)
print(div)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
