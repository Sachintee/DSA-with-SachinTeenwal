--- ❤️ ---

# 🚀 _Day 194. Validating Roman Numerals_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/validating-roman-numerals/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <regex>
#include <string>
using namespace std;

bool is_valid_roman(const string& s) {
    static const regex pattern("^M{0,3}(CM|CD|D?C{0,3})(XC|XL|L?X{0,3})(IX|IV|V?I{0,3})$");
    return regex_match(s, pattern);
}

int main() {
    int N;
    cin >> N;
    cin.ignore(); // To ignore the newline after N
    for (int i = 0; i < N; ++i) {
        string line;
        getline(cin, line);
        if (is_valid_roman(line)) {
            cout << "YES" << endl;
        } else {
            cout << "NO" << endl;
        }
    }
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class Main {
    public static boolean isValidRoman(String s) {
        String pattern = "^M{0,3}(CM|CD|D?C{0,3})(XC|XL|L?X{0,3})(IX|IV|V?I{0,3})$";
        return Pattern.matches(pattern, s);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        scanner.nextLine(); // To consume the newline after N
        for (int i = 0; i < N; ++i) {
            String line = scanner.nextLine();
            if (isValidRoman(line)) {
                System.out.println("YES");
            } else {
                System.out.println("NO");
            }
        }
        scanner.close();
    }
}
```

## Code (Python)

```python
import re

def is_valid_roman(s):
    pattern = r'^M{0,3}(CM|CD|D?C{0,3})(XC|XL|L?X{0,3})(IX|IV|V?I{0,3})$'
    return bool(re.fullmatch(pattern, s))

def main():
    import sys
    input_lines = sys.stdin.read().splitlines()
    N = int(input_lines[0])
    for line in input_lines[1:N+1]:
        if is_valid_roman(line.strip()):
            print("YES")
        else:
            print("NO")

if __name__ == '__main__':
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
