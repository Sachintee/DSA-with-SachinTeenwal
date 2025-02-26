---
Difficulty: Hard  
Source: 160 Days of Problem Solving  
Tags:
  - Stack
  - sliding-window
---

# 🚀 _Day 57. Maximum of minimum for every window size_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/stack-gfg-160/problem/maximum-of-minimum-for-every-window-size3453)  

## 💡 **Problem Description:**

Given an array of integers **arr[]**, find the **maximum of the minimum element** for every window size **w** from **1 to N**.  

## Code(C++)
```cpp
class Solution {
public:
    vector<int> maxOfMins(vector<int>& arr) {
        int n = arr.size();
        vector<int> res(n), len(n);
        stack<int> s;
        for (int i = 0; i <= n; i++) {
            while (!s.empty() && (i == n || arr[s.top()] >= arr[i])) {
                int j = s.top();
                s.pop();
                len[j] = s.empty() ? i : i - s.top() - 1;
            }
            if (i < n) s.push(i);
        }
        for (int i = 0; i < n; i++) res[len[i] - 1] = max(res[len[i] - 1], arr[i]);
        for (int i = n - 2; i >= 0; i--) res[i] = max(res[i], res[i + 1]);
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> maxOfMins(int[] arr) {
        int n = arr.length;
        int[] res = new int[n], len = new int[n];
        Stack<Integer> s = new Stack<>();
        for (int i = 0; i <= n; i++) {
            while (!s.isEmpty() && (i == n || arr[s.peek()] >= arr[i])) {
                int j = s.pop();
                len[j] = s.isEmpty() ? i : i - s.peek() - 1;
            }
            if (i < n) s.push(i);
        }
        for (int i = 0; i < n; i++) res[len[i] - 1] = Math.max(res[len[i] - 1], arr[i]);
        for (int i = n - 2; i >= 0; i--) res[i] = Math.max(res[i], res[i + 1]);
        ArrayList<Integer> ans = new ArrayList<>();
        for (int r : res) ans.add(r);
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxOfMins(self, arr):
        n = len(arr)
        res, length, s = [0] * n, [0] * n, []
        for i in range(n + 1):
            while s and (i == n or arr[s[-1]] >= arr[i]):
                j = s.pop()
                length[j] = i if not s else i - s[-1] - 1
            if i < n:
                s.append(i)
        for i in range(n):
            res[length[i] - 1] = max(res[length[i] - 1], arr[i])
        for i in range(n - 2, -1, -1):
            res[i] = max(res[i], res[i + 1])
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
