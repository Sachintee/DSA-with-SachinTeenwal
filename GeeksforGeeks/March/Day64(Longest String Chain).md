---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
---

# 🚀 _Day 64. Longest String Chain_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/longest-string-chain)  


## 💡 **Problem Description:**

You are given an array of words where each word consists of lowercase English letters.


## Code(C++)
```cpp
class Solution {
public:
    int longestStringChain(vector<string>& words) {
        sort(words.begin(), words.end(), [](const string &a, const string &b) {
            return a.size() < b.size();
        });
        unordered_map<string, int> dp;
        int res = 1;
        for (auto &w : words) {
            dp[w] = 1;
            for (int i = 0; i < w.size(); i++) {
                string pred = w.substr(0, i) + w.substr(i + 1);
                if (dp.count(pred)) dp[w] = max(dp[w], dp[pred] + 1);
            }
            res = max(res, dp[w]);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int longestStringChain(String[] words) {
        Arrays.sort(words, Comparator.comparingInt(String::length));
        Map<String, Integer> dp = new HashMap<>();
        int res = 1;
        for (String w : words) {
            dp.put(w, 1);
            for (int i = 0; i < w.length(); i++) {
                String pred = w.substring(0, i) + w.substring(i + 1);
                dp.put(w, Math.max(dp.get(w), dp.getOrDefault(pred, 0) + 1));
            }
            res = Math.max(res, dp.get(w));
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestStringChain(self, words):
        words.sort(key=len)
        dp = {}
        res = 1
        for w in words:
            dp[w] = 1
            for i in range(len(w)):
                pred = w[:i] + w[i+1:]
                if pred in dp:
                    dp[w] = max(dp[w], dp[pred] + 1)
            res = max(res, dp[w])
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
