--- ❤️ ---

# 🚀 _Day 112. Fraction_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/fraction/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    string fractionToDecimal(int numerator, int denominator) {
        if (numerator == 0) return "0";

        string result;

        // Determine the sign
        if ((numerator < 0) ^ (denominator < 0)) result += "-";

        // Use long to handle overflow
        long num = labs(numerator);
        long den = labs(denominator);

        // Add the integral part
        result += to_string(num / den);
        long remainder = num % den;
        if (remainder == 0) return result;

        result += ".";
        unordered_map<long, int> map;

        while (remainder != 0) {
            if (map.find(remainder) != map.end()) {
                result.insert(map[remainder], "(");
                result += ")";
                break;
            }

            map[remainder] = result.length();
            remainder *= 10;
            result += to_string(remainder / den);
            remainder %= den;
        }

        return result;
    }
};

```

## Code (Java)

```java
import java.util.*;

class Solution {
    public String fractionToDecimal(int numerator, int denominator) {
        if (numerator == 0) return "0";

        StringBuilder result = new StringBuilder();

        // Handle sign
        if ((numerator < 0) ^ (denominator < 0)) result.append("-");

        long num = Math.abs((long) numerator);
        long den = Math.abs((long) denominator);

        // Integral part
        result.append(num / den);
        long remainder = num % den;
        if (remainder == 0) return result.toString();

        result.append(".");
        Map<Long, Integer> map = new HashMap<>();

        while (remainder != 0) {
            if (map.containsKey(remainder)) {
                int index = map.get(remainder);
                result.insert(index, "(");
                result.append(")");
                break;
            }

            map.put(remainder, result.length());
            remainder *= 10;
            result.append(remainder / den);
            remainder %= den;
        }

        return result.toString();
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : integer (numerator)
    # @param B : integer (denominator)
    # @return a string
    def fractionToDecimal(self, A, B):
        if A == 0:
            return "0"

        result = []

        # Determine the sign
        if (A < 0) ^ (B < 0):
            result.append("-")

        # Convert to long to avoid overflow and work with abs
        num = abs(A)
        den = abs(B)

        # Add the integral part
        result.append(str(num // den))
        remainder = num % den

        if remainder == 0:
            return ''.join(result)

        result.append(".")
        # Dictionary to store remainders and their positions
        remainder_map = {}

        while remainder != 0:
            # If the remainder is already seen, it means a repeating cycle starts
            if remainder in remainder_map:
                index = remainder_map[remainder]
                result.insert(index, "(")
                result.append(")")
                break

            # Store the current position of remainder
            remainder_map[remainder] = len(result)

            remainder *= 10
            result.append(str(remainder // den))
            remainder %= den

        return ''.join(result)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
