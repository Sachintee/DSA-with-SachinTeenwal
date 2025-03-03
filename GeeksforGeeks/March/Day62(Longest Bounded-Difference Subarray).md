---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - sliding-window
  - Heap
  - Arrays
  - Queue
---

# 🚀 _Day 62. Longest Bounded-Difference Subarray_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/queue-and-deque-gfg-160/problem/longest-bounded-difference-subarray)


## 💡 **Problem Description:**

Given an array of positive integers `arr[]` and a non-negative integer `x`, the task is to find the **longest sub-array** where the absolute difference between any two elements is not greater than `x`.  

If multiple such subarrays exist, return the one that **starts at the smallest index**.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> longestSubarray(vector<int>& arr, int x) {
        deque<int> minQ, maxQ;
        int n = arr.size(), start = 0, resStart = 0, resEnd = 0;
        for (int end = 0; end < n; end++) {
            while (!minQ.empty() && arr[minQ.back()] > arr[end]) minQ.pop_back();
            while (!maxQ.empty() && arr[maxQ.back()] < arr[end]) maxQ.pop_back();
            minQ.push_back(end), maxQ.push_back(end);
            while (arr[maxQ.front()] - arr[minQ.front()] > x) {
                if (minQ.front() == start) minQ.pop_front();
                if (maxQ.front() == start) maxQ.pop_front();
                start++;
            }
            if (end - start > resEnd - resStart) resStart = start, resEnd = end;
        }
        return vector<int>(arr.begin() + resStart, arr.begin() + resEnd + 1);
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> longestSubarray(int[] arr, int x) {
        Deque<Integer> minQ = new ArrayDeque<>(), maxQ = new ArrayDeque<>();
        int n = arr.length, start = 0, resStart = 0, resLen = 0;
        for (int end = 0; end < n; end++) {
            while (!minQ.isEmpty() && arr[minQ.peekLast()] > arr[end]) minQ.pollLast();
            while (!maxQ.isEmpty() && arr[maxQ.peekLast()] < arr[end]) maxQ.pollLast();
            minQ.addLast(end);
            maxQ.addLast(end);
            while (arr[maxQ.peekFirst()] - arr[minQ.peekFirst()] > x) {
                if (minQ.peekFirst() == start) minQ.pollFirst();
                if (maxQ.peekFirst() == start) maxQ.pollFirst();
                start++;
            }
            if (end - start + 1 > resLen) {
                resStart = start;
                resLen = end - start + 1;
            }
        }
        ArrayList<Integer> res = new ArrayList<>();
        for (int i = resStart; i < resStart + resLen; i++) res.add(arr[i]);
        return res;
    }
}
```

## Code (Python)

```python
from collections import deque

class Solution:
    def longestSubarray(self, arr, x):
        minQ, maxQ, start, resStart, resEnd = deque(), deque(), 0, 0, 0
        for end in range(len(arr)):
            while minQ and arr[minQ[-1]] > arr[end]: minQ.pop()
            while maxQ and arr[maxQ[-1]] < arr[end]: maxQ.pop()
            minQ.append(end), maxQ.append(end)
            while arr[maxQ[0]] - arr[minQ[0]] > x:
                if minQ[0] == start: minQ.popleft()
                if maxQ[0] == start: maxQ.popleft()
                start += 1
            if end - start > resEnd - resStart: resStart, resEnd = start, end
        return arr[resStart:resEnd + 1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
