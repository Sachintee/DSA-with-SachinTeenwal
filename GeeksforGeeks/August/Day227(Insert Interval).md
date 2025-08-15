---
title: "🗓️ Insert Interval | GFG Solution 🔍"
keywords🏷️: ["🗓️ insert interval", "🔍 interval merging", "📍 two pointers", "📈 array manipulation", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Insert Interval problem: efficiently insert and merge overlapping intervals in a sorted array using linear traversal technique. 🚀"
date: 📅 2025-08-13
---

# *227. Insert Interval*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/insert-interval-1666733333/1)

## **🧩 Problem Description**

Geek has an array of non-overlapping intervals `intervals[][]` where `intervals[i] = [starti, endi]` represent the start and the end of the ith event and intervals is sorted in ascending order by `starti`. He wants to add a new interval `newInterval[] = [newStart, newEnd]` where `newStart` and `newEnd` represent the start and end of this interval.

Help Geek to insert `newInterval` into intervals such that intervals is still sorted in ascending order by `starti` and intervals still does not have any overlapping intervals (merge overlapping intervals if necessary).


## Code(C++)
```cpp
class Solution {
public:
    vector<vector<int>> insertInterval(vector<vector<int>>& intervals, vector<int>& newInterval) {
        vector<vector<int>> result;
        int i = 0, n = intervals.size();
        
        while (i < n && intervals[i][1] < newInterval[0]) result.push_back(intervals[i++]);
        while (i < n && intervals[i][0] <= newInterval[1]) {
            newInterval[0] = min(newInterval[0], intervals[i][0]);
            newInterval[1] = max(newInterval[1], intervals[i++][1]);
        }
        result.push_back(newInterval);
        while (i < n) result.push_back(intervals[i++]);
        
        return result;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<int[]> insertInterval(int[][] intervals, int[] newInterval) {
        ArrayList<int[]> result = new ArrayList<>();
        int i = 0;
        while (i < intervals.length && intervals[i][1] < newInterval[0])
            result.add(intervals[i++]);
        
        while (i < intervals.length && intervals[i][0] <= newInterval[1]) {
            newInterval[0] = Math.min(newInterval[0], intervals[i][0]);
            newInterval[1] = Math.max(newInterval[1], intervals[i++][1]);
        }
        result.add(newInterval);
        
        while (i < intervals.length) result.add(intervals[i++]);
        
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    def insertInterval(self, intervals, newInterval):
        result = []
        i = 0
        while i < len(intervals) and intervals[i][1] < newInterval[0]:
            result.append(intervals[i])
            i += 1
        
        while i < len(intervals) and intervals[i][0] <= newInterval[1]:
            newInterval[0] = min(newInterval[0], intervals[i][0])
            newInterval[1] = max(newInterval[1], intervals[i][1])
            i += 1
        result.append(newInterval)
        
        while i < len(intervals):
            result.append(intervals[i])
            i += 1
            
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
