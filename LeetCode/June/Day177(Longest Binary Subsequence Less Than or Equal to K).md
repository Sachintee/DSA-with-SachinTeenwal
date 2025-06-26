--- ❤️ ---

# 🚀 _Day 177. Longest Binary Subsequence Less Than or Equal to K_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/longest-binary-subsequence-less-than-or-equal-to-k/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int longestSubsequence(string s, int k) {
        int ans = 0, v = 0;
        for (int i = s.size() - 1; ~i; --i) {
            if (s[i] == '0') {
                ++ans;
            } else if (ans < 30 && (v | 1 << ans) <= k) {
                v |= 1 << ans;
                ++ans;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int longestSubsequence(String s, int k) {
        int ans = 0, v = 0;
        for (int i = s.length() - 1; i >= 0; --i) {
            if (s.charAt(i) == '0') {
                ++ans;
            } else if (ans < 30 && (v | 1 << ans) <= k) {
                v |= 1 << ans;
                ++ans;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestSubsequence(self, s: str, k: int) -> int:
        ans = v = 0
        for c in s[::-1]:
            if c == "0":
                ans += 1
            elif ans < 30 and (v | 1 << ans) <= k:
                v |= 1 << ans
                ans += 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
