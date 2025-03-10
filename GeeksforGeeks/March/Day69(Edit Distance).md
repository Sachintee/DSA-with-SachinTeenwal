---
Difficulty: Hard  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
  - Strings
---

# 🚀 _Day 69. Edit Distance_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/edit-distance3702)  

## 💡 **Problem Description:**

Given two strings **s1** and **s2**, you need to find the minimum number of operations required to convert **s1** into **s2**. The valid operations are:  
1. **Insert** a character at any position.  
2. **Delete** any character from the string.  
3. **Replace** any character with another character.  


## Code(C++)
```cpp
class Solution {
public:
    int editDistance(string& s1, string& s2) {
        int m = s1.size(), n = s2.size();
        vector<int> prev(n + 1), curr(n + 1);
        iota(prev.begin(), prev.end(), 0);
        for (int i = 1; i <= m; i++) {
            curr[0] = i;
            for (int j = 1; j <= n; j++)
                curr[j] = s1[i-1] == s2[j-1] ? prev[j-1] : 1 + min({prev[j-1], prev[j], curr[j-1]});
            swap(prev, curr);
        }
        return prev[n];
    }
};
```

## Code (Java)

```java
class Solution {
    public int editDistance(String s1, String s2) {
        int m = s1.length(), n = s2.length();
        int[] prev = new int[n + 1], curr = new int[n + 1];
        for (int i = 0; i <= n; i++) prev[i] = i;
        for (int i = 1; i <= m; i++) {
            curr[0] = i;
            for (int j = 1; j <= n; j++)
                curr[j] = s1.charAt(i-1) == s2.charAt(j-1) ? prev[j-1] : 1 + Math.min(prev[j-1], Math.min(prev[j], curr[j-1]));
            int[] temp = prev;
            prev = curr;
            curr = temp;
        }
        return prev[n];
    }
}
```

## Code (Python)

```python
class Solution:
    def editDistance(self, s1, s2):
        m, n = len(s1), len(s2)
        prev, curr = list(range(n + 1)), [0] * (n + 1)
        for i in range(1, m + 1):
            curr[0] = i
            for j in range(1, n + 1):
                curr[j] = prev[j-1] if s1[i-1] == s2[j-1] else 1 + min(prev[j-1], prev[j], curr[j-1])
            prev, curr = curr, prev
        return prev[n]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
