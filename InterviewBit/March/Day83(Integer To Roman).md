--- ❤️ ---

# 🚀 _Day 83. Integer To Roman_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/integer-to-roman/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>
using namespace std;

class Solution {
public:
    string intToRoman(int num) {
        vector<pair<int, string>> val = {
            {1000, "M"},
            {900, "CM"},
            {500, "D"},
            {400, "CD"},
            {100, "C"},
            {90, "XC"},
            {50, "L"},
            {40, "XL"},
            {10, "X"},
            {9, "IX"},
            {5, "V"},
            {4, "IV"},
            {1, "I"}
        };
        string roman;
        for (const auto &[value, symbol] : val) {
            while (num >= value) {
                roman += symbol;
                num -= value;
            }
            if (num == 0) break;
        }
        return roman;
    }
};
```

## Code (Java)

```java
import java.util.List;
import java.util.ArrayList;
import java.util.AbstractMap.SimpleEntry;

public class Solution {
    public String intToRoman(int num) {
        List<SimpleEntry<Integer, String>> val = new ArrayList<>();
        val.add(new SimpleEntry<>(1000, "M"));
        val.add(new SimpleEntry<>(900, "CM"));
        val.add(new SimpleEntry<>(500, "D"));
        val.add(new SimpleEntry<>(400, "CD"));
        val.add(new SimpleEntry<>(100, "C"));
        val.add(new SimpleEntry<>(90, "XC"));
        val.add(new SimpleEntry<>(50, "L"));
        val.add(new SimpleEntry<>(40, "XL"));
        val.add(new SimpleEntry<>(10, "X"));
        val.add(new SimpleEntry<>(9, "IX"));
        val.add(new SimpleEntry<>(5, "V"));
        val.add(new SimpleEntry<>(4, "IV"));
        val.add(new SimpleEntry<>(1, "I"));

        StringBuilder roman = new StringBuilder();
        for (SimpleEntry<Integer, String> entry : val) {
            int value = entry.getKey();
            String symbol = entry.getValue();
            while (num >= value) {
                roman.append(symbol);
                num -= value;
            }
            if (num == 0) break;
        }
        return roman.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def intToRoman(self, A):
        val = [
            (1000, 'M'),
            (900, 'CM'),
            (500, 'D'),
            (400, 'CD'),
            (100, 'C'),
            (90, 'XC'),
            (50, 'L'),
            (40, 'XL'),
            (10, 'X'),
            (9, 'IX'),
            (5, 'V'),
            (4, 'IV'),
            (1, 'I')
        ]
        roman_num = []
        for num, symbol in val:
            while A >= num:
                roman_num.append(symbol)
                A -= num
            if A == 0:
                break
        return ''.join(roman_num)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
