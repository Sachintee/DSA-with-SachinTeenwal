--- ❤️ ---

# 🚀 _Day 101. Count Symmetric Integers_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-symmetric-integers/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countSymmetricIntegers(int low, int high) {
        int ans = 0;
        auto f = [](int x) {
            string s = to_string(x);
            int n = s.size();
            if (n & 1) {
                return 0;
            }
            int a = 0, b = 0;
            for (int i = 0; i < n / 2; ++i) {
                a += s[i] - '0';
                b += s[n / 2 + i] - '0';
            }
            return a == b ? 1 : 0;
        };
        for (int x = low; x <= high; ++x) {
            ans += f(x);
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countSymmetricIntegers(int low, int high) {
        int ans = 0;
        for (int x = low; x <= high; ++x) {
            ans += f(x);
        }
        return ans;
    }

    private int f(int x) {
        String s = "" + x;
        int n = s.length();
        if (n % 2 == 1) {
            return 0;
        }
        int a = 0, b = 0;
        for (int i = 0; i < n / 2; ++i) {
            a += s.charAt(i) - '0';
        }
        for (int i = n / 2; i < n; ++i) {
            b += s.charAt(i) - '0';
        }
        return a == b ? 1 : 0;
    }
}
```

## Code (Python)

```python
class Solution:
    def countSymmetricIntegers(self, low: int, high: int) -> int:
        def f(x: int) -> bool:
            s = str(x)
            if len(s) & 1:
                return False
            n = len(s) // 2
            return sum(map(int, s[:n])) == sum(map(int, s[n:]))

        return sum(f(x) for x in range(low, high + 1))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
