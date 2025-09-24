--- ❤️ ---

# 🚀 _Day 267. Regex in JS_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/regex-in-js/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
#include <regex>
using namespace std;

int main() {
    string Str, Patt;
    getline(cin, Str);
    getline(cin, Patt);
    
    // Create regex pattern with case-insensitive flag
    regex pattern(Patt, regex_constants::icase);
    
    // Search for pattern in string
    bool result = regex_search(Str, pattern);
    
    cout << (result ? "true" : "false") << endl;
    
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String Str = scanner.nextLine().trim();
        String Patt = scanner.nextLine().trim();
        
        // Create pattern with CASE_INSENSITIVE flag
        Pattern pattern = Pattern.compile(Patt, Pattern.CASE_INSENSITIVE);
        Matcher matcher = pattern.matcher(Str);
        
        // Check if pattern is found
        boolean result = matcher.find();
        
        System.out.println(result);
        
        scanner.close();
    }
}
```

## Code (Python)

```python
import re

Str = input().strip()
Patt = input().strip()

# Using re.IGNORECASE flag for case-insensitive search
print(str(bool(re.search(Patt, Str, re.I))).lower())
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
