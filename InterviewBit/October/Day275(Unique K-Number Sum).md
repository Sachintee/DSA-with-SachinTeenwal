---
title: "🔢 Unique K-Number Sum | GFG Solution 🔍"  
keywords🏷️: ["🔢 combination sum", "🔍 backtracking", "📍 recursion", "📈 DFS", "📘 GFG", "🏁 competitive programming", "📚 DSA"]  
description: "✅ GFG solution to the Unique K-Number Sum problem: find all valid combinations of k distinct numbers from 1-9 that sum to n using backtracking and DFS techniques. 🚀"  
date: 📅 2025-10-02  
---

# *275. Unique K-Number Sum*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/combination-sum-iii--111703/1)

## **🧩 Problem Description**

You are given two integers `n` and `k`. Your task is to find all valid combinations of `k` numbers that add up to `n` based on the following conditions:

- Only numbers from the range **[1, 9]** can be used.
- Each number can only be used **at most once**.

A valid combination is a set of `k` distinct numbers from 1 to 9 whose sum equals `n`. The goal is to return all such combinations.


## Code(C++)
```cpp
class Solution {
public:
    vector<vector<int>> combinationSum(int n, int k) {
        if (n < k || n > 9 * k) return {};
        vector<vector<int>> res;
        vector<int> cur;
        function<void(int, int, int)> dfs = [&](int start, int sum, int cnt) {
            if (cnt == k) {
                if (sum == n) res.push_back(cur);
                return;
            }
            for (int i = start; i <= 9; i++) {
                if (sum + i > n) break;
                cur.push_back(i);
                dfs(i + 1, sum + i, cnt + 1);
                cur.pop_back();
            }
        };
        dfs(1, 0, 0);
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<ArrayList<Integer>> combinationSum(int n, int k) {
        ArrayList<ArrayList<Integer>> res = new ArrayList<>();
        if (n < k || n > 9 * k) return res;
        backtrack(res, new ArrayList<>(), n, k, 1);
        return res;
    }
    
    void backtrack(ArrayList<ArrayList<Integer>> res, ArrayList<Integer> cur, int rem, int left, int start) {
        if (left == 0) {
            if (rem == 0) res.add(new ArrayList<>(cur));
            return;
        }
        for (int i = start; i <= 9; i++) {
            if (rem < i) break;
            cur.add(i);
            backtrack(res, cur, rem - i, left - 1, i + 1);
            cur.remove(cur.size() - 1);
        }
    }
}
```

## Code (Python)

```python
class Solution:
    def combinationSum(self, n, k):
        if n < k or n > 9 * k: return []
        res = []
        def bt(start, rem, left, cur):
            if left == 0:
                if rem == 0: res.append(cur[:])
                return
            for i in range(start, 10):
                if rem < i: break
                cur.append(i)
                bt(i + 1, rem - i, left - 1, cur)
                cur.pop()
        bt(1, n, k, [])
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
