---
Difficulty: Hard  
Source: 160 Days of Problem Solving  
Tags:
  - Stack
---

# 🚀 _Day 56. Histogram Max Rectangular Area_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/stack-gfg-160/problem/maximum-rectangular-area-in-a-histogram-1587115620)  

## 💡 **Problem Description:**

You are given a **histogram** represented by an array `arr`, where each element denotes the **height** of the bars.  
Each bar has a width of **1 unit**.  


## Code(C++)
```cpp
class Solution {
public:
    int getMaxArea(vector<int>& arr) {
        stack<int> s;
        int n = arr.size(), res = 0;
        for (int i = 0; i <= n; i++) {
            while (!s.empty() && (i == n || arr[s.top()] >= arr[i])) {
                int h = arr[s.top()];
                s.pop();
                int w = s.empty() ? i : i - s.top() - 1;
                res = max(res, h * w);
            }
            s.push(i);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int getMaxArea(int[] arr) {
        Stack<Integer> s = new Stack<>();
        int n = arr.length, res = 0;
        for (int i = 0; i <= n; i++) {
            while (!s.isEmpty() && (i == n || arr[s.peek()] >= arr[i])) {
                int h = arr[s.pop()];
                int w = s.isEmpty() ? i : i - s.peek() - 1;
                res = Math.max(res, h * w);
            }
            s.push(i);
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def getMaxArea(self, arr):
        stack, n, res = [], len(arr), 0
        for i in range(n + 1):
            while stack and (i == n or arr[stack[-1]] >= arr[i]):
                h = arr[stack.pop()]
                w = i if not stack else i - stack[-1] - 1
                res = max(res, h * w)
            stack.append(i)
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
