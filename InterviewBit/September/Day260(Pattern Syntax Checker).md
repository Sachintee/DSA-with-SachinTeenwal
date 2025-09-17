--- ❤️ ---

# 🚀 _Day 260. Pattern Syntax Checker_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/pattern-syntax-checker/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <regex>
using namespace std;

int main() {
    int testCases;
    cin >> testCases;
    cin.ignore();  // To ignore the newline after the integer input

    while (testCases--) {
        string pattern;
        getline(cin, pattern);
        try {
            regex re(pattern);
            cout << "Valid" << endl;
        } catch (regex_error& e) {
            cout << "Invalid" << endl;
        }
    }

    return 0;
}

```

## Code (Java)

```java
import java.util.*;
import java.util.regex.*;

public class Main {
    public static void main(String[] args) {
        
        Scanner in = new Scanner(System.in);
        int testCases = Integer.parseInt(in.nextLine());
        
        while (testCases-- > 0) {
            String pattern = in.nextLine();
            try {
                Pattern.compile(pattern);
                System.out.println("Valid");
            } catch (PatternSyntaxException e) {
                System.out.println("Invalid");
            }
        }
        
        in.close();
    }
}

```

## Code (Python3)

```python
import re

test_cases = int(input())

for _ in range(test_cases):
    pattern = input()
    try:
        re.compile(pattern)
        print("Valid")
    except re.error:
        print("Invalid")

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
