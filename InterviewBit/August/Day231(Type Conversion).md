--- ❤️ ---

# 🚀 _Day 231. Type Conversion_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/type-conversion/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include<iostream>

using namespace std;

int main()  {
    char ch;
    cin>>ch;
    int asciiValue = ch; // Implicit conversion from char to int
    cout << asciiValue;
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        char ch = scanner.next().charAt(0);
        int asciiValue = (int) ch;
        System.out.println(asciiValue);
    }
}
```

## Code (Python)

```python
ch = input().strip()
print(ord(ch))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
