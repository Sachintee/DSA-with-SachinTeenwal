---
title: "💼 Weighted Job Scheduling | GFG Solution 🔍"
keywords🏷️: ["💼 weighted job scheduling", "📊 dynamic programming", "🔍 binary search", "📈 optimization", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Weighted Job Scheduling problem: maximize profit by scheduling non-overlapping jobs using dynamic programming and binary search. 🚀"
date: 📅 2025-11-07
---

# *311. Weighted Job Scheduling*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/weighted-job-scheduling/1)

## **🧩 Problem Description**

You are given a 2D array `jobs[][]` of size `n × 3`, where each row represents a single job with the following details:

- `jobs[i][0]`: Start time of the job
- `jobs[i][1]`: End time of the job  
- `jobs[i][2]`: Profit earned by completing the job

Your task is to find the **maximum profit** you can earn by scheduling **non-overlapping jobs**.


## Code(C++)
```cpp
class Solution {
public:
    int maxProfit(vector<vector<int>> &jobs) {
        sort(jobs.begin(), jobs.end());
        int n = jobs.size();
        vector<int> dp(n + 1, 0);
        for (int i = n - 1; i >= 0; i--) {
            int l = i + 1, r = n - 1, nxt = n;
            while (l <= r) {
                int m = (l + r) / 2;
                if (jobs[m][0] >= jobs[i][1]) {
                    nxt = m;
                    r = m - 1;
                } else {
                    l = m + 1;
                }
            }
            dp[i] = max(jobs[i][2] + dp[nxt], dp[i + 1]);
        }
        return dp[0];
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxProfit(int[][] jobs) {
        Arrays.sort(jobs, (a, b) -> a[0] - b[0]);
        int n = jobs.length;
        int[] dp = new int[n + 1];
        for (int i = n - 1; i >= 0; i--) {
            int l = i + 1, r = n - 1, nxt = n;
            while (l <= r) {
                int m = (l + r) / 2;
                if (jobs[m][0] >= jobs[i][1]) {
                    nxt = m;
                    r = m - 1;
                } else {
                    l = m + 1;
                }
            }
            dp[i] = Math.max(jobs[i][2] + dp[nxt], dp[i + 1]);
        }
        return dp[0];
    }
}
```

## Code (Python)

```python
class Solution: 
    def maxProfit(self, jobs):
        jobs.sort()
        n = len(jobs)
        dp = [0] * (n + 1)
        for i in range(n - 1, -1, -1):
            l, r, nxt = i + 1, n - 1, n
            while l <= r:
                m = (l + r) // 2
                if jobs[m][0] >= jobs[i][1]:
                    nxt = m
                    r = m - 1
                else:
                    l = m + 1
            dp[i] = max(jobs[i][2] + dp[nxt], dp[i + 1])
        return dp[0]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
