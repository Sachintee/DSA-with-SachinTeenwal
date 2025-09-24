--- ❤️ ---

# 🚀 _Day 267. Fraction to Recurring Decimal_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/fraction-to-recurring-decimal/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    string fractionToDecimal(int numerator, int denominator) {
        if (numerator == 0) {
            return "0";
        }
        string ans;
        bool neg = (numerator > 0) ^ (denominator > 0);
        if (neg) {
            ans += "-";
        }
        long long a = abs(1LL * numerator), b = abs(1LL * denominator);
        ans += to_string(a / b);
        a %= b;
        if (a == 0) {
            return ans;
        }
        ans += ".";
        unordered_map<long long, int> d;
        while (a) {
            d[a] = ans.size();
            a *= 10;
            ans += to_string(a / b);
            a %= b;
            if (d.contains(a)) {
                ans.insert(d[a], "(");
                ans += ")";
                break;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public String fractionToDecimal(int numerator, int denominator) {
        if (numerator == 0) {
            return "0";
        }
        StringBuilder sb = new StringBuilder();
        boolean neg = (numerator > 0) ^ (denominator > 0);
        sb.append(neg ? "-" : "");
        long a = Math.abs((long) numerator), b = Math.abs((long) denominator);
        sb.append(a / b);
        a %= b;
        if (a == 0) {
            return sb.toString();
        }
        sb.append(".");
        Map<Long, Integer> d = new HashMap<>();
        while (a != 0) {
            d.put(a, sb.length());
            a *= 10;
            sb.append(a / b);
            a %= b;
            if (d.containsKey(a)) {
                sb.insert(d.get(a), "(");
                sb.append(")");
                break;
            }
        }
        return sb.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def fractionToDecimal(self, numerator: int, denominator: int) -> str:
        if numerator == 0:
            return "0"
        ans = []
        neg = (numerator > 0) ^ (denominator > 0)
        if neg:
            ans.append("-")
        a, b = abs(numerator), abs(denominator)
        ans.append(str(a // b))
        a %= b
        if a == 0:
            return "".join(ans)
        ans.append(".")
        d = {}
        while a:
            d[a] = len(ans)
            a *= 10
            ans.append(str(a // b))
            a %= b
            if a in d:
                ans.insert(d[a], "(")
                ans.append(")")
                break
        return "".join(ans)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
