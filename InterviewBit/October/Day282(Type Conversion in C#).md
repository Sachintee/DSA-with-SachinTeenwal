--- ❤️ ---

# 🚀 _Day 282. Type Conversion in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/type-conversion-in-c/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    char ch;
    cin >> ch;
    
    // Convert character to ASCII value
    int asciiValue = (int)ch;
    
    cout << asciiValue << endl;
    
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
        
        // Convert character to ASCII value
        int asciiValue = (int)ch;
        
        System.out.println(asciiValue);
        
        scanner.close();
    }
}
```

## Code (Python)

```python
# Read input character
ch = input()

# Convert character to ASCII value using ord() function
ascii_value = ord(ch)

print(ascii_value)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
