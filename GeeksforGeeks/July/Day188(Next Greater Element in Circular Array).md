---
title: "🔄 Next Greater Element in Circular Array | GFG Solution 🔍"
keywords🏷️: ["🔄 circular array", "📚 stack", "🔍 next greater element", "📈 monotonic stack", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
]description: "✅ GFG solution to the Next Greater Element in Circular Array problem: find the next greater element for each element in a circular array using monotonic stack technique. 🚀"
date: 📅 2025-07-07
---

# *188. Next Greater Element in Circular Array*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/next-greater-element/1)

## **🧩 Problem Description**

Given a circular integer array `arr[]`, the task is to determine the **next greater element (NGE)** for each element in the array.

The next greater element of an element `arr[i]` is the first element that is greater than `arr[i]` when traversing circularly. If no such element exists, return -1 for that position.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> nextLargerElement(vector<int>& arr) {
        int n = arr.size();
        vector<int> res(n, -1);
        stack<int> st;
        for (int i = 2 * n - 1; i >= 0; i--) {
            while (!st.empty() && st.top() <= arr[i % n]) st.pop();
            if (i < n && !st.empty()) res[i] = st.top();
            st.push(arr[i % n]);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> nextLargerElement(int[] arr) {
        int n = arr.length;
        ArrayList<Integer> res = new ArrayList<>(Collections.nCopies(n, -1));
        Deque<Integer> st = new ArrayDeque<>();
        for (int i = 2 * n - 1; i >= 0; i--) {
            while (!st.isEmpty() && st.peek() <= arr[i % n]) st.pop();
            if (i < n && !st.isEmpty()) res.set(i, st.peek());
            st.push(arr[i % n]);
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def nextLargerElement(self, arr):
        n = len(arr)
        res = [-1] * n
        st = []
        for i in range(2 * n - 1, -1, -1):
            while st and st[-1] <= arr[i % n]:
                st.pop()
            if i < n and st:
                res[i] = st[-1]
            st.append(arr[i % n])
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
