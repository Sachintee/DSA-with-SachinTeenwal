# *135. Substrings with Same First and Last Characters*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/substrings-with-similar-first-and-last-characters3644/1)


## **🧩 Problem Description**

Given a string `s` consisting of lowercase English letters, count all substrings in which the first and last characters are the same.

A substring is a contiguous sequence of characters within the string. Single-character substrings are always valid.
# 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    int countSubstring(string &s) {
        long long cnt[256]={}, ans=0;
        for(char c:s) cnt[(unsigned char)c]++;
        for(int i=0;i<256;i++)
            ans += cnt[i]*(cnt[i]+1)/2;
        return (int)ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countSubstring(String s) {
        int[] cnt = new int[256];
        long ans = 0;
        for (char c : s.toCharArray()) cnt[c]++;
        for (int x : cnt) ans += (long)x * (x + 1) / 2;
        return (int)ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def countSubstring(self, s):
        from collections import Counter
        return sum(v * (v + 1) // 2 for v in Counter(s).values())
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
