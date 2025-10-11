--- ❤️ ---

# 🚀 _Day 284. Strings in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/strings-in-c/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
// Method 2: Using algorithms for counting
#include <iostream>
#include <string>
#include <algorithm>
using namespace std;

int main() {
    string str;
    getline(cin, str);
    
    cout << str.length() << endl;
    cout << (int)str.find('a') << endl; // automatically converts npos to -1
    cout << count(str.begin(), str.end(), 'b') << endl;
    
    if (str.length() > 4) {
        cout << str.substr(2, 3) << endl;
    } else {
        cout << (str.length() > 2 ? str.substr(2) : "") << endl;
    }
    
    cout << boolalpha << (str == "InterviewBit") << endl;
    return 0;
}
```

## Code (Java)

```java
// Method 2: Using Java 8 streams for counting
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String str = scanner.nextLine();
        
        System.out.println(str.length());
        System.out.println(str.indexOf('a'));
        System.out.println(str.chars().filter(ch -> ch == 'b').count());
        
        System.out.println(str.length() > 4 ? str.substring(2, 5) : 
                          str.length() > 2 ? str.substring(2) : "");
        System.out.println(str.equals("InterviewBit"));
        scanner.close();
    }
}
```

## Code (Python)

```python
# Method 2: More concise Python version
str_input = input()

print(len(str_input))
print(str_input.find('a'))
print(str_input.count('b'))
print(str_input[2:5] if len(str_input) > 4 else str_input[2:] if len(str_input) > 2 else "")
print(str_input == "InterviewBit")
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
