---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - sliding-window
  - Arrays
  - Queue
---

# 🚀 _Day 61. K Sized Subarray Maximum_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/queue-and-deque-gfg-160/problem/maximum-of-all-subarrays-of-size-k3101)


## 💡 **Problem Description:**

Given an **array arr[]** of integers and an integer **k**, your task is to find the **maximum value for each contiguous subarray of size k**. The output should be an array of maximum values corresponding to each contiguous subarray.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> maxOfSubarrays(const vector<int>& arr, int k) {
        vector<int> res;
        deque<int> dq;
        for (int i = 0; i < arr.size(); ++i) {
            if (!dq.empty() && dq.front() <= i - k) dq.pop_front();
            while (!dq.empty() && arr[dq.back()] < arr[i]) dq.pop_back();
            dq.push_back(i);
            if (i >= k - 1) res.push_back(arr[dq.front()]);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> maxOfSubarrays(int[] arr, int k) {
        ArrayList<Integer> res = new ArrayList<>();
        Deque<Integer> dq = new ArrayDeque<>();
        for (int i = 0; i < arr.length; i++) {
            if (!dq.isEmpty() && dq.peekFirst() <= i - k) dq.pollFirst();
            while (!dq.isEmpty() && arr[dq.peekLast()] < arr[i]) dq.pollLast();
            dq.offerLast(i);
            if (i >= k - 1) res.add(arr[dq.peekFirst()]);
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxOfSubarrays(self, arr, k):
        res, dq = [], deque()
        for i in range(len(arr)):
            if dq and dq[0] <= i - k:
                dq.popleft()
            while dq and arr[dq[-1]] < arr[i]:
                dq.pop()
            dq.append(i)
            if i >= k - 1:
                res.append(arr[dq[0]])
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
