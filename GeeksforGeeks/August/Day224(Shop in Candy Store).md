---
title: "🍭 Shop in Candy Store | GFG Solution 🛒"
keywords🏷️: ["🍭 candy store", "🎯 greedy algorithm", "📊 sorting", "💰 min max cost", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Shop in Candy Store problem: find minimum and maximum cost to buy all candies with free candy offer using greedy approach. 🚀"
date: 📅 2025-08-12
---

# *224. Shop in Candy Store*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/shop-in-candy-store1145/1)

## **🧩 Problem Description**

In a candy store, there are different types of candies available and `prices[i]` represent the price of `ith` types of candies. You are provided with an attractive offer: **For every candy you buy from the store, you can get up to k other different candies for free.**

Your task is to find the **minimum and maximum amount of money** needed to buy all the candies.

**Note:** In both cases, you must take the maximum number of free candies possible during each purchase.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> minMaxCandy(vector<int>& prices, int k) {
        sort(prices.begin(), prices.end());
        int n = prices.size(), min = 0, max = 0;
        for (int i = 0, rem = n; i < rem; i++, rem -= k) min += prices[i];
        for (int j = n - 1, idx = -1; j > idx; j--, idx += k) max += prices[j];
        return {min, max};
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> minMaxCandy(int[] prices, int k) {
        Arrays.sort(prices);
        int n = prices.length, min = 0, max = 0;
        for (int i = 0, rem = n; i < rem; i++, rem -= k) min += prices[i];
        for (int j = n - 1, idx = -1; j > idx; j--, idx += k) max += prices[j];
        return new ArrayList<>(Arrays.asList(min, max));
    }
}
```

## Code (Python)

```python
class Solution:
    def minMaxCandy(self, prices, k):
        prices.sort()
        n, min_, max_ = len(prices), 0, 0
        i, rem = 0, n
        while i < rem:
            min_ += prices[i]; i += 1; rem -= k
        j, idx = n - 1, -1
        while j > idx:
            max_ += prices[j]; j -= 1; idx += k
        return [min_, max_]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
