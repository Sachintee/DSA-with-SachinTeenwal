---
title: "🔮 Maximum Non-Overlapping Odd Palindrome Sum | GFG Solution 🎯"
keywords🏷️: ["🔮 palindrome", "🎯 string processing", "📈 dynamic programming", "🧮 manacher algorithm", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Maximum Non-Overlapping Odd Palindrome Sum problem: find maximum sum of lengths of two non-overlapping odd palindromes using Manacher's algorithm. 🚀"
date: 📅 2025-08-11
---

# *223. Maximum Non-Overlapping Odd Palindrome Sum*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximum-non-overlapping-odd-palindrome-sum/1)

## **🧩 Problem Description**

Given a string `s` consisting of lowercase English letters, find the maximum possible sum of the lengths of any two **non-empty** and **non-overlapping** palindromic substrings of **odd length**.

Formally, choose any two substrings `s[i...j]` and `s[k...l]` such that `1 ≤ i ≤ j < k ≤ l ≤ s.size()`, both substrings are palindromes of odd length, and they do not overlap. Return the maximum sum of their lengths.

**Note:** A palindrome is a string that reads the same forward and backward. A substring is a contiguous sequence of characters within the string.


## Code(C++)
```cpp
class Solution {
public:
    int maxSum(string& s) {
        int n = s.size();
        vector<int> left(n, 1), right(n, 1), rad(n);
        
        for (int i = 0, l = 0, r = -1; i < n; i++) {
            int k = (i > r) ? 1 : min(rad[l + r - i], r - i + 1);
            while (i - k >= 0 && i + k < n && s[i - k] == s[i + k]) k++;
            rad[i] = k--;
            if (i + k > r) l = i - k, r = i + k;
        }
        
        for (int i = 0; i < n; i++) {
            int len = rad[i] * 2 - 1;
            int end = i + rad[i] - 1;
            if (end < n) left[end] = max(left[end], len);
        }
        
        for (int i = n - 2; i >= 0; i--) left[i] = max(left[i], left[i + 1] - 2);
        for (int i = 1; i < n; i++) left[i] = max(left[i], left[i - 1]);
        
        for (int i = n - 1; i >= 0; i--) {
            int len = rad[i] * 2 - 1;
            int start = i - rad[i] + 1;
            if (start >= 0) right[start] = max(right[start], len);
        }
        
        for (int i = 1; i < n; i++) right[i] = max(right[i], right[i - 1] - 2);
        for (int i = n - 2; i >= 0; i--) right[i] = max(right[i], right[i + 1]);
        
        int ans = 1;
        for (int i = 0; i + 1 < n; i++) ans = max(ans, left[i] + right[i + 1]);
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxSum(String s) {
        int n = s.length();
        int[] left = new int[n], right = new int[n], rad = new int[n];
        Arrays.fill(left, 1);
        Arrays.fill(right, 1);
        
        for (int i = 0, l = 0, r = -1; i < n; i++) {
            int k = (i > r) ? 1 : Math.min(rad[l + r - i], r - i + 1);
            while (i - k >= 0 && i + k < n && s.charAt(i - k) == s.charAt(i + k)) k++;
            rad[i] = k--;
            if (i + k > r) { l = i - k; r = i + k; }
        }
        
        for (int i = 0; i < n; i++) {
            int len = rad[i] * 2 - 1;
            int end = i + rad[i] - 1;
            if (end < n) left[end] = Math.max(left[end], len);
        }
        
        for (int i = n - 2; i >= 0; i--) left[i] = Math.max(left[i], left[i + 1] - 2);
        for (int i = 1; i < n; i++) left[i] = Math.max(left[i], left[i - 1]);
        
        for (int i = n - 1; i >= 0; i--) {
            int len = rad[i] * 2 - 1;
            int start = i - rad[i] + 1;
            if (start >= 0) right[start] = Math.max(right[start], len);
        }
        
        for (int i = 1; i < n; i++) right[i] = Math.max(right[i], right[i - 1] - 2);
        for (int i = n - 2; i >= 0; i--) right[i] = Math.max(right[i], right[i + 1]);
        
        int ans = 1;
        for (int i = 0; i + 1 < n; i++) ans = Math.max(ans, left[i] + right[i + 1]);
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxSum(self, s):
        n = len(s)
        left, right, rad = [1] * n, [1] * n, [0] * n
        l, r = 0, -1
        for i in range(n):
            k = 1 if i > r else min(rad[l + r - i], r - i + 1)
            while i - k >= 0 and i + k < n and s[i - k] == s[i + k]:
                k += 1
            rad[i] = k
            k -= 1
            if i + k > r:
                l, r = i - k, i + k

        for i in range(n):
            length = rad[i] * 2 - 1
            end = i + rad[i] - 1
            if end < n:
                left[end] = max(left[end], length)
        
        for i in range(n - 2, -1, -1):
            left[i] = max(left[i], left[i + 1] - 2)
        for i in range(1, n):
            left[i] = max(left[i], left[i - 1])
        
        for i in range(n - 1, -1, -1):
            length = rad[i] * 2 - 1
            start = i - rad[i] + 1
            if start >= 0:
                right[start] = max(right[start], length)
        
        for i in range(1, n):
            right[i] = max(right[i], right[i - 1] - 2)
        for i in range(n - 2, -1, -1):
            right[i] = max(right[i], right[i + 1])
        
        ans = 1
        for i in range(n - 1):
            ans = max(ans, left[i] + right[i + 1])
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
