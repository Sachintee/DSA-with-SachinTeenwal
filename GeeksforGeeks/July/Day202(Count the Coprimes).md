---
title: "🔢 Count the Coprimes | GFG Solution 🔍"
keywords🏷️: ["🔢 gcd", "🟰 co-prime pairs", "🔍 mobius function", "📈 number theory", "📍 inclusion exclusion", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Count the Coprimes problem: count pairs with GCD=1 using Möbius function and inclusion-exclusion principle for efficient computation. 🚀"
date: 📅 2025-07-21
---

# *202. Count the Coprimes*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/count-the-coprimes/1)

## **🧩 Problem Description**

You are given an array `arr[]` of positive integers. Your task is to count the number of pairs `(i, j)` such that:

- `0 ≤ i < j ≤ n-1`
- `gcd(arr[i], arr[j]) = 1`

In other words, count the number of unordered pairs of indices `(i, j)` where the elements at those positions are co-prime (their greatest common divisor is 1).

## Code(C++)
```cpp
class Solution {
public:
    int cntCoprime(vector<int>& arr) {
        int mx = *max_element(arr.begin(), arr.end());
        vector<int> cnt(mx + 1), div(mx + 1), mu(mx + 1, 1);
        vector<bool> vis(mx + 1);
        
        for (int x : arr) cnt[x]++;

        for (int i = 1; i <= mx; ++i)
            for (int j = i; j <= mx; j += i)
                div[i] += cnt[j];

        for (int i = 2; i <= mx; ++i) {
            if (!vis[i]) {
                for (int j = i; j <= mx; j += i) {
                    mu[j] *= -1;
                    vis[j] = 1;
                }
                for (long long j = (long long)i * i; j <= mx; j += (long long)i * i)
                    mu[j] = 0;
            }
        }

        int ans = 0;
        for (int i = 1; i <= mx; ++i)
            if (mu[i] && div[i] > 1)
                ans += mu[i] * div[i] * (div[i] - 1) / 2;
        
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    int cntCoprime(int[] arr) {
        int mx = Arrays.stream(arr).max().orElse(0);
        int[] cnt = new int[mx + 1], div = new int[mx + 1], mu = new int[mx + 1];
        boolean[] vis = new boolean[mx + 1];
        
        for (int x : arr) cnt[x]++;
        
        Arrays.fill(mu, 1);
        for (int i = 2; i <= mx; ++i) {
            if (!vis[i]) {
                for (int j = i; j <= mx; j += i) {
                    mu[j] *= -1;
                    vis[j] = true;
                }
                for (long j = (long)i * i; j <= mx; j += (long)i * i)
                    mu[(int)j] = 0;
            }
        }
        
        for (int i = 1; i <= mx; ++i)
            for (int j = i; j <= mx; j += i)
                div[i] += cnt[j];
        
        int ans = 0;
        for (int i = 1; i <= mx; ++i)
            if (mu[i] != 0 && div[i] > 1)
                ans += mu[i] * div[i] * (div[i] - 1) / 2;
        
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def cntCoprime(self, arr):
        mx = max(arr)
        cnt, div, mu = [0] * (mx + 1), [0] * (mx + 1), [1] * (mx + 1)
        vis = [False] * (mx + 1)
        
        for x in arr:
            cnt[x] += 1
        
        for i in range(2, mx + 1):
            if not vis[i]:
                for j in range(i, mx + 1, i):
                    mu[j] *= -1
                    vis[j] = True
                for j in range(i * i, mx + 1, i * i):
                    mu[j] = 0
        
        for i in range(1, mx + 1):
            for j in range(i, mx + 1, i):
                div[i] += cnt[j]
        
        ans = 0
        for i in range(1, mx + 1):
            if mu[i] and div[i] > 1:
                ans += mu[i] * div[i] * (div[i] - 1) // 2
        
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
