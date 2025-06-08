---
title: "➕ Sum String | GFG Solution 🧮"
keywords🏷️: ["➕ string addition", "🧮 sum string", "🔄 recursion", "🧑‍💻 string manipulation", "📚 GFG", "🧑‍🏫 learning recursion", "🧑‍💻 manual addition"]
description: "✅ GFG solution to the Sum String problem: check if a numeric string follows a sum sequence using string addition and recursion. 🚀"
date: 📅 2025-06-08
---

# *08. Sum-String*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/sum-string3151/1)





## Code(C++)
```cpp
class Solution {
  public:
    string addStrings(string a, string b) {
        if (a.size() < b.size()) swap(a, b);
        int carry = 0, n = a.size(), m = b.size();
        string res = "";
        for (int i = 0; i < m; ++i) {
            int s = (a[n - 1 - i] - '0') + (b[m - 1 - i] - '0') + carry;
            res = char(s % 10 + '0') + res;
            carry = s / 10;
        }
        for (int i = m; i < n; ++i) {
            int s = (a[n - 1 - i] - '0') + carry;
            res = char(s % 10 + '0') + res;
            carry = s / 10;
        }
        if (carry) res = char(carry + '0') + res;
        return res;
    }

    bool check(string &s, int i, int l1, int l2) {
        string x = s.substr(i, l1), y = s.substr(i + l1, l2);
        if ((x[0] == '0' && l1 > 1) || (y[0] == '0' && l2 > 1)) return false;
        string sum = addStrings(x, y);
        int l3 = sum.size();
        if (i + l1 + l2 + l3 > s.size()) return false;
        if (sum != s.substr(i + l1 + l2, l3)) return false;
        if (i + l1 + l2 + l3 == s.size()) return true;
        return check(s, i + l1, l2, l3);
    }

    bool isSumString(string &s) {
        int n = s.size();
        for (int l1 = 1; l1 < n; ++l1)
            for (int l2 = 1; l1 + l2 < n; ++l2)
                if (check(s, 0, l1, l2)) return true;
        return false;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean isSumString(String s) {
        int n = s.length();
        for (int l1 = 1; l1 < n; l1++) {
            for (int l2 = 1; l1 + l2 < n; l2++) {
                if (check(s, 0, l1, l2)) return true;
            }
        }
        return false;
    }

    boolean check(String s, int i, int l1, int l2) {
        String x = s.substring(i, i + l1), y = s.substring(i + l1, i + l1 + l2);
        if ((x.length() > 1 && x.charAt(0) == '0') || (y.length() > 1 && y.charAt(0) == '0')) return false;
        String sum = add(x, y);
        int l3 = sum.length();
        if (i + l1 + l2 + l3 > s.length()) return false;
        String z = s.substring(i + l1 + l2, i + l1 + l2 + l3);
        if (!sum.equals(z)) return false;
        if (i + l1 + l2 + l3 == s.length()) return true;
        return check(s, i + l1, l2, l3);
    }

    String add(String a, String b) {
        if (a.length() < b.length()) return add(b, a);
        StringBuilder sb = new StringBuilder();
        int carry = 0, n = a.length(), m = b.length();
        for (int i = 0; i < m; i++) {
            int s = (a.charAt(n - 1 - i) - '0') + (b.charAt(m - 1 - i) - '0') + carry;
            sb.append(s % 10);
            carry = s / 10;
        }
        for (int i = m; i < n; i++) {
            int s = (a.charAt(n - 1 - i) - '0') + carry;
            sb.append(s % 10);
            carry = s / 10;
        }
        if (carry > 0) sb.append(carry);
        return sb.reverse().toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def isSumString(self, s: str) -> bool:
        def add(a, b):
            return str(int(a) + int(b))
        
        def check(i, l1, l2):
            x, y = s[i:i + l1], s[i + l1:i + l1 + l2]
            if (len(x) > 1 and x[0] == '0') or (len(y) > 1 and y[0] == '0'):
                return False
            z = add(x, y)
            l3 = len(z)
            if i + l1 + l2 + l3 > len(s): return False
            if s[i + l1 + l2:i + l1 + l2 + l3] != z: return False
            if i + l1 + l2 + l3 == len(s): return True
            return check(i + l1, l2, l3)

        n = len(s)
        for l1 in range(1, n):
            for l2 in range(1, n - l1):
                if check(0, l1, l2): return True
        return False
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
