---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
  - Binary Search
---

# 🚀 _Day 63. Longest Increasing Subsequence_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/longest-increasing-subsequence-1587115620)  


## 💡 **Problem Description:**

Given an array **arr[]** of non-negative integers, the task is to find the length of the **Longest Strictly Increasing Subsequence (LIS)**.

A **subsequence** is strictly increasing if each element in the subsequence is strictly less than the next element.


## Code(C++)
```cpp
class Solution {
public:
    int lis(std::vector<int>& arr) {
        std::vector<int> ans;
        for (int num : arr) {
            auto it = std::lower_bound(ans.begin(), ans.end(), num);
            if (it == ans.end()) ans.push_back(num);
            else *it = num;
        }
        return ans.size();
    }
};
```

## Code (Java)

```java
class Solution {
    public int lis(int[] arr) {
        ArrayList<Integer> ans = new ArrayList<>();
        for (int num : arr) {
            int idx = Collections.binarySearch(ans, num);
            if (idx < 0) idx = -idx - 1;
            if (idx == ans.size()) ans.add(num);
            else ans.set(idx, num);
        }
        return ans.size();
    }
}
```

## Code (Python)

```python
import bisect

class Solution:
    def lis(self, arr):
        ans = []
        for num in arr:
            idx = bisect.bisect_left(ans, num)
            if idx == len(ans):
                ans.append(num)
            else:
                ans[idx] = num
        return len(ans)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
