---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Greedy
---

# 🚀 _Day 90. Maximize partitions in a String_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/greedy-gfg-160/problem/maximize-partitions-in-a-string)  

## 💡 **Problem Description:** 

Given a string **s** consisting of lowercase English alphabets, your task is to determine the **maximum number of substrings** that can be formed by partitioning **s** such that **no two substrings share common characters**.


## Code(C++)
```cpp
class Solution {
public:
    int maxPartitions(string &s) {
        int ans = 0, end = 0;
        vector<int> last(26);
        for (int i = 0; i < s.size(); i++) 
            last[s[i] - 'a'] = i;
        for (int i = 0; i < s.size(); i++) {
            end = max(end, last[s[i] - 'a']);
            if (i == end) ans++;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxPartitions(String s) {
        int[] last = new int[26];
        for (int i = 0; i < s.length(); i++) 
            last[s.charAt(i) - 'a'] = i;
        int count = 0, end = 0;
        for (int i = 0; i < s.length(); i++) {
            end = Math.max(end, last[s.charAt(i) - 'a']);
            if (i == end)
                count++;
        }
        return count;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxPartitions(self, s: str) -> int:
        last = {c: i for i, c in enumerate(s)}
        count = end = 0
        for i, c in enumerate(s):
            end = max(end, last[c])
            if i == end:
                count += 1
        return count
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
