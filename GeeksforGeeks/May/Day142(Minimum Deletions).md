# *142. Minimum Deletions*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/minimum-deletitions1648/1)


## **🧩 Problem Description**

Given a string `s`, the task is to determine the minimum number of characters that must be **deleted** from `s` to convert it into a **palindrome**. The **relative order of remaining characters must be preserved**.

To solve this, we must **maximize** the length of the longest palindromic subsequence (LPS) and subtract its length from the original string length.

### 💬 Key Insight:

* The minimum number of deletions = `len(s) - LPS(s)`
* Where **LPS(s)** is the length of the **Longest Palindromic Subsequence** of `s`.



## Code(C++)
```cpp
class Solution {
  public:
    int minDeletions(string &s) {
        int n = s.size();
        vector<int> dp(n), prev(n);
        for (int i = n - 1; i >= 0; --i) {
            dp[i] = 1;
            for (int j = i + 1; j < n; ++j)
                dp[j] = s[i] == s[j] ? prev[j - 1] + 2 : max(prev[j], dp[j - 1]);
            prev = dp;
        }
        return n - dp[n - 1];
    }
};
```

## Code (Java)

```java
class Solution {
    static int minDeletions(String s) {
        int n = s.length();
        int[] dp = new int[n], prev = new int[n];
        for (int i = n - 1; i >= 0; --i) {
            dp[i] = 1;
            for (int j = i + 1; j < n; ++j)
                dp[j] = s.charAt(i) == s.charAt(j) ? prev[j - 1] + 2 : Math.max(prev[j], dp[j - 1]);
            prev = dp.clone();
        }
        return n - dp[n - 1];
    }
}
```

## Code (Python)

```python
class Solution:
    def minDeletions(self, s):
        n = len(s)
        dp = [0] * n
        prev = [0] * n
        for i in range(n - 1, -1, -1):
            dp[i] = 1
            for j in range(i + 1, n):
                dp[j] = prev[j - 1] + 2 if s[i] == s[j] else max(prev[j], dp[j - 1])
            prev = dp[:]
        return n - dp[-1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
