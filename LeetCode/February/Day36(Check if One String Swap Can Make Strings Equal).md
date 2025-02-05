--- ❤️ ---

# 🚀 _Day 36. Check if One String Swap Can Make Strings Equal_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/check-if-one-string-swap-can-make-strings-equal/submissions/1532429219/?envType=daily-question&envId=2025-02-05)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    bool areAlmostEqual(string s1, string s2) {
        int cnt = 0;
        char c1 = 0, c2 = 0;
        for (int i = 0; i < s1.size(); ++i) {
            char a = s1[i], b = s2[i];
            if (a != b) {
                if (++cnt > 2 || (cnt == 2 && (a != c2 || b != c1))) {
                    return false;
                }
                c1 = a, c2 = b;
            }
        }
        return cnt != 1;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean areAlmostEqual(String s1, String s2) {
        int cnt = 0;
        char c1 = 0, c2 = 0;
        for (int i = 0; i < s1.length(); ++i) {
            char a = s1.charAt(i), b = s2.charAt(i);
            if (a != b) {
                if (++cnt > 2 || (cnt == 2 && (a != c2 || b != c1))) {
                    return false;
                }
                c1 = a;
                c2 = b;
            }
        }
        return cnt != 1;
    }
}
```

## Code (Python)

```python
class Solution:
    def areAlmostEqual(self, s1: str, s2: str) -> bool:
        cnt = 0
        c1 = c2 = None
        for a, b in zip(s1, s2):
            if a != b:
                cnt += 1
                if cnt > 2 or (cnt == 2 and (a != c2 or b != c1)):
                    return False
                c1, c2 = a, b
        return cnt != 1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
