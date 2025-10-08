--- ❤️ ---

# 🚀 _Day 281. StringBuilder in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/stringbuilder-in-c/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    // Declare a string (C++ doesn't have StringBuilder, but string is mutable)
    string str;
    
    // Append "Interview"
    str.append("Interview");
    
    // Append "Bit" with newline
    str.append("Bit\n");
    
    // Append "C# Course"
    str.append("C# Course");
    
    // Print the current string
    cout << str;
    
    // Replace "Interview" with "C# "
    size_t pos = str.find("Interview");
    if (pos != string::npos) {
        str.replace(pos, 9, "C# "); // 9 is length of "Interview"
    }
    
    // Print the current string
    cout << str;
    
    // Print the length of the string
    cout << str.length() << endl;
    
    return 0;
}
```

## Code (Java)

```java
public class Main {
    public static void main(String[] args) {
        // Declare a StringBuilder
        StringBuilder sb = new StringBuilder();
        
        // Append "Interview"
        sb.append("Interview");
        
        // AppendLine "Bit" (Java uses append with newline)
        sb.append("Bit\n");
        
        // Append "C# Course"
        sb.append("C# Course");
        
        // Print the current StringBuilder
        System.out.print(sb);
        
        // Replace "Interview" with "C# "
        int index = sb.indexOf("Interview");
        if (index != -1) {
            sb.replace(index, index + "Interview".length(), "C# ");
        }
        
        // Print the current StringBuilder
        System.out.print(sb);
        
        // Print the length of the StringBuilder
        System.out.println(sb.length());
    }
}
```

## Code (Python)

```python
# Declare a string (Python strings are immutable, but we can use concatenation or lists)
# Using list as mutable alternative to StringBuilder
sb_list = []

# Append "Interview"
sb_list.append("Interview")

# Append "Bit" with newline
sb_list.append("Bit\n")

# Append "C# Course"
sb_list.append("C# Course")

# Join and print the current string
current_str = ''.join(sb_list)
print(current_str, end='')

# Replace "Interview" with "C# "
current_str = current_str.replace("Interview", "C# ")

# Print the current string
print(current_str, end='')

# Print the length of the string
print(len(current_str))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
