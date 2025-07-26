---
title: "🗳️ Majority Element II | GFG Solution 🔍"
keywords🏷️: ["🔢 majority element", "🗳️ voting algorithm", "📈 boyer moore", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Majority Element II problem: find all elements appearing more than n/3 times using Boyer-Moore Majority Vote algorithm. 🚀"
date: 📅 2025-07-26
---

# *207. Majority Element II*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/majority-vote/1)

## **🧩 Problem Description**

You are given an array of integer `arr[]` where each number represents a vote to a candidate. Return the candidates that have votes **greater than one-third of the total votes**. If there's not a majority vote, return an empty array.

**Note:** The answer should be returned in an increasing format.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> findMajority(vector<int>& arr) {
        int n = arr.size(), a = 0, b = 1, ca = 0, cb = 0;
        for (int x : arr) {
            if (x == a) ca++;
            else if (x == b) cb++;
            else if (!ca) a = x, ca = 1;
            else if (!cb) b = x, cb = 1;
            else ca--, cb--;
        }
        ca = cb = 0;
        for (int x : arr) {
            if (x == a) ca++;
            else if (x == b) cb++;
        }
        vector<int> res;
        if (ca > n / 3) res.push_back(a);
        if (cb > n / 3 && a != b) res.push_back(b);
        sort(res.begin(), res.end());
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> findMajority(int[] arr) {
        int n = arr.length, a = 0, b = 1, ca = 0, cb = 0;
        for (int x : arr) {
            if (x == a) ca++;
            else if (x == b) cb++;
            else if (ca == 0) { a = x; ca = 1; }
            else if (cb == 0) { b = x; cb = 1; }
            else { ca--; cb--; }
        }
        ca = cb = 0;
        for (int x : arr) {
            if (x == a) ca++;
            else if (x == b) cb++;
        }
        ArrayList<Integer> res = new ArrayList<>();
        if (ca > n / 3) res.add(a);
        if (cb > n / 3 && a != b) res.add(b);
        Collections.sort(res);
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def findMajority(self, arr):
        n, a, b, ca, cb = len(arr), 0, 1, 0, 0
        for x in arr:
            if x == a: ca += 1
            elif x == b: cb += 1
            elif ca == 0: a, ca = x, 1
            elif cb == 0: b, cb = x, 1
            else: ca, cb = ca - 1, cb - 1
        ca = cb = 0
        for x in arr:
            if x == a: ca += 1
            elif x == b: cb += 1
        res = []
        if ca > n // 3: res.append(a)
        if cb > n // 3 and a != b: res.append(b)
        return sorted(res)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
