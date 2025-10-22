--- ❤️ ---

# 🚀 _Day 295. Valid phone number_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/valid-phone-number/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <fstream>
#include <regex>
#include <string>
using namespace std;

int main() {
    ifstream file("input"); // read from file named 'input'
    string line;
    regex pattern1("^\\(\\d{3}\\) \\d{3}-\\d{4}$"); // (xxx) xxx-xxxx
    regex pattern2("^\\d{3}-\\d{3}-\\d{4}$");       // xxx-xxx-xxxx

    while (getline(file, line)) {
        if (regex_match(line, pattern1) || regex_match(line, pattern2)) {
            cout << line << endl;
        }
    }

    return 0;
}

```

## Code (Java)

```java
import java.io.*;
import java.util.regex.*;

public class Main {
    public static void main(String[] args) throws Exception {
        BufferedReader br = new BufferedReader(new FileReader("input"));
        String line;
        
        Pattern pattern1 = Pattern.compile("^\\(\\d{3}\\) \\d{3}-\\d{4}$"); // (xxx) xxx-xxxx
        Pattern pattern2 = Pattern.compile("^\\d{3}-\\d{3}-\\d{4}$");       // xxx-xxx-xxxx

        while ((line = br.readLine()) != null) {
            if (pattern1.matcher(line).matches() || pattern2.matcher(line).matches()) {
                System.out.println(line);
            }
        }

        br.close();
    }
}

```

## Code (Python)

```python
import re

def main():
    # Open and read from 'input' file
    with open('input', 'r') as file:
        lines = file.readlines()

    # Define regex patterns for valid phone numbers
    pattern1 = re.compile(r'^\(\d{3}\) \d{3}-\d{4}$')   # (xxx) xxx-xxxx
    pattern2 = re.compile(r'^\d{3}-\d{3}-\d{4}$')       # xxx-xxx-xxxx

    # Check each line and print valid numbers
    for line in lines:
        line = line.strip()
        if pattern1.match(line) or pattern2.match(line):
            print(line)

if __name__ == '__main__':
    main()

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
