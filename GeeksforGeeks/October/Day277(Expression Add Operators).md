---
title: "🧮 Expression Add Operators | GFG Solution 🔍"
keywords🏷️: ["🧮 expression add operators", "🔍 backtracking", "📍 recursion", "💡 DFS", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Expression Add Operators problem: insert +, -, * between digits to reach a target value using DFS & backtracking. 🚀"
date: 📅 2025-10-04
---


# *277. Expression Add Operators*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/expression-add-operators/1)

## **🧩 Problem Description**

Given a string `s` that contains only digits (0-9) and an integer `target`, return all possible strings by inserting the binary operators `'+'`, `'-'`, and/or `'*'` between the digits of `s` such that the resultant expression evaluates to the target value.


## Code(C++)
```cpp
class Solution {
public:
    vector<string> findExpr(string& s, int target) {
        vector<string> res;
        function<void(int, long, long, string)> dfs = [&](int i, long val, long prev, string path) {
            if (i == s.size()) {
                if (val == target) res.push_back(path);
                return;
            }
            for (int j = i; j < s.size(); j++) {
                if (j > i && s[i] == '0') break;
                long cur = stol(s.substr(i, j - i + 1));
                if (i == 0) dfs(j + 1, cur, cur, to_string(cur));
                else {
                    dfs(j + 1, val + cur, cur, path + "+" + to_string(cur));
                    dfs(j + 1, val - cur, -cur, path + "-" + to_string(cur));
                    dfs(j + 1, val - prev + prev * cur, prev * cur, path + "*" + to_string(cur));
                }
            }
        };
        dfs(0, 0, 0, "");
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<String> findExpr(String s, int target) {
        ArrayList<String> res = new ArrayList<>();
        dfs(s, target, 0, 0, 0, "", res);
        return res;
    }
    void dfs(String s, int target, int i, long val, long prev, String path, ArrayList<String> res) {
        if (i == s.length()) {
            if (val == target) res.add(path);
            return;
        }
        for (int j = i; j < s.length(); j++) {
            if (j > i && s.charAt(i) == '0') break;
            long cur = Long.parseLong(s.substring(i, j + 1));
            if (i == 0) dfs(s, target, j + 1, cur, cur, "" + cur, res);
            else {
                dfs(s, target, j + 1, val + cur, cur, path + "+" + cur, res);
                dfs(s, target, j + 1, val - cur, -cur, path + "-" + cur, res);
                dfs(s, target, j + 1, val - prev + prev * cur, prev * cur, path + "*" + cur, res);
            }
        }
    }
}
```

## Code (Python)

```python
class Solution:
    def findExpr(self, s, target):
        res = []
        def dfs(i, val, prev, path):
            if i == len(s):
                if val == target: res.append(path)
                return
            for j in range(i, len(s)):
                if j > i and s[i] == '0': break
                cur = int(s[i:j+1])
                if i == 0: dfs(j + 1, cur, cur, str(cur))
                else:
                    dfs(j + 1, val + cur, cur, path + '+' + str(cur))
                    dfs(j + 1, val - cur, -cur, path + '-' + str(cur))
                    dfs(j + 1, val - prev + prev * cur, prev * cur, path + '*' + str(cur))
        dfs(0, 0, 0, '')
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
