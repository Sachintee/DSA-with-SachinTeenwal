---
title: "🔄 Next Greater Element in Circular Array | GFG Solution 🔍"
keywords🏷️: ["🔄 circular array", "🔍 stack", "📍 next greater element", "📈 monotonic stack", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Next Greater Element in Circular Array problem: find next greater element for each position in circular array using monotonic stack technique. 🚀"
date: 📅 2025-09-18
---

# *261. Next Greater Element in Circular Array*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/next-greater-element/1)

## **🧩 Problem Description**

Given a circular integer array `arr[]`, the task is to determine the **next greater element (NGE)** for each element in the array.

The next greater element of an element `arr[i]` is the first element that is greater than `arr[i]` when traversing circularly. If no such element exists, return -1 for that position.

**Note:** Since the array is circular, after reaching the last element, the search continues from the beginning until we have looked at all elements once.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> nextGreater(vector<int> &arr) {
        int n = arr.size();
        vector<int> res(n, -1);
        stack<int> stk;
        for (int i = 0; i < 2 * n; i++) {
            while (!stk.empty() && arr[stk.top()] < arr[i % n]) {
                res[stk.top()] = arr[i % n];
                stk.pop();
            }
            if (i < n) stk.push(i);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> nextGreater(int[] arr) {
        int n = arr.length;
        ArrayList<Integer> res = new ArrayList<>(Collections.nCopies(n, -1));
        Stack<Integer> stk = new Stack<>();
        for (int i = 0; i < 2 * n; i++) {
            while (!stk.isEmpty() && arr[stk.peek()] < arr[i % n]) {
                res.set(stk.pop(), arr[i % n]);
            }
            if (i < n) stk.push(i);
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def nextGreater(self, arr):
        n = len(arr)
        res = [-1] * n
        stk = []
        for i in range(2 * n):
            while stk and arr[stk[-1]] < arr[i % n]:
                res[stk.pop()] = arr[i % n]
            if i < n:
                stk.append(i)
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
