---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
---

# 🚀 _Day 85. Word Break_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/word-break1352)  

## 💡 **Problem Description:** 

You are given a string `s` and a list `dictionary[]` of words. Your task is to determine whether the string `s` can be formed by concatenating one or more words from the `dictionary[]`.  

**Note:** From `dictionary[]`, any word can be taken any number of times and in any order.  


## Code(C++)
```cpp
class Solution {
public:
    bool wordBreak(string s, vector<string>& d) {
        unordered_set<string> u(d.begin(), d.end());
        int n = s.size(), m = 0;
        for(auto &w : d) m = max(m, (int)w.size());
        vector<bool> dp(n + 1);
        dp[0] = 1;
        for(int i = 0; i < n; i++) {
            if(!dp[i]) continue;
            for(int j = 1; j <= m && i + j <= n; j++)
                if(u.count(s.substr(i, j))) dp[i + j] = 1;
        }
        return dp[n];
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean wordBreak(String s, String[] d) {
        Set<String> set = new HashSet<>(Arrays.asList(d));
        int n = s.length(), m = 0;
        for (String w : d) m = Math.max(m, w.length());
        boolean[] dp = new boolean[n + 1];
        dp[0] = true;
        for (int i = 0; i < n; i++) {
            if (!dp[i]) continue;
            for (int j = 1; j <= m && i + j <= n; j++)
                if (set.contains(s.substring(i, i + j))) dp[i + j] = true;
        }
        return dp[n];
    }
}
```

## Code (Python)

```python
class Solution:
    def wordBreak(self, s, dictionary):
        d = set(dictionary)
        m = max((len(w) for w in dictionary), default=0)
        n = len(s)
        dp = [False] * (n + 1)
        dp[0] = True
        for i in range(n):
            if not dp[i]:
                continue
            for j in range(1, m + 1):
                if i + j <= n and s[i:i + j] in d:
                    dp[i + j] = True
        return dp[n]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
