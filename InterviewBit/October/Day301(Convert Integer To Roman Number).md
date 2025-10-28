--- ❤️ ---

# 🚀 _Day 301. Convert Integer To Roman Number_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/convert-integer-to-roman-number/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <fstream>
#include <vector>
using namespace std;

string intToRoman(int num) {
    vector<int> values = {1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1};
    vector<string> symbols = {"M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"};
    string roman = "";
    for (int i = 0; i < values.size(); i++) {
        while (num >= values[i]) {
            roman += symbols[i];
            num -= values[i];
        }
    }
    return roman;
}

int main() {
    ifstream file("input");
    int num;
    while (file >> num) {
        cout << intToRoman(num) << endl;
    }
    return 0;
}

```

## Code (Java)

```java
import java.io.*;
import java.util.*;

public class Main {
    public static String intToRoman(int num) {
        int[] values = {1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1};
        String[] symbols = {"M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"};
        StringBuilder roman = new StringBuilder();
        for (int i = 0; i < values.length; i++) {
            while (num >= values[i]) {
                roman.append(symbols[i]);
                num -= values[i];
            }
        }
        return roman.toString();
    }

    public static void main(String[] args) throws Exception {
        BufferedReader br = new BufferedReader(new FileReader("input"));
        String line;
        while ((line = br.readLine()) != null) {
            line = line.trim();
            if (line.isEmpty()) continue;
            int num = Integer.parseInt(line);
            System.out.println(intToRoman(num));
        }
        br.close();
    }
}

```

## Code (Python)

```python
def int_to_roman(num):
    values = [1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1]
    symbols = ["M", "CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"]
    roman = ""
    for i in range(len(values)):
        while num >= values[i]:
            roman += symbols[i]
            num -= values[i]
    return roman

def main():
    with open("input", "r") as file:
        for line in file:
            line = line.strip()
            if not line:
                continue
            num = int(line)
            print(int_to_roman(num))

if __name__ == "__main__":
    main()

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
