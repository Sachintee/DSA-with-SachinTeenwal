---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Greedy
  - Binary Search
---

# 🚀 _Day 87. Activity Selection_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/greedy-gfg-160/problem/activity-selection-1587115620)  


## 💡 **Problem Description:** 

You are given a set of activities, each with a **start time** and a **finish time**, represented by the arrays `start[]` and `finish[]`, respectively. A single person can perform only **one activity at a time**, meaning no two activities can overlap.  

Your task is to determine the **maximum number of activities** that a person can complete in a day.  


## Code(C++)
```cpp
class Solution {
public:
    int activitySelection(vector<int> &start, vector<int> &finish) {
        vector<pair<int, int>> arr;
        for (int i = 0; i < start.size(); i++) 
            arr.emplace_back(finish[i], start[i]);
        sort(arr.begin(), arr.end());
        int ans = 0, finishtime = -1;
        for (auto &activity : arr) 
            if (activity.second > finishtime) 
                finishtime = activity.first, ans++;
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int activitySelection(int[] start, int[] finish) {
        int n = start.length, ans = 0, finishtime = -1;
        Integer[] indices = new Integer[n];
        for (int i = 0; i < n; i++) indices[i] = i;
        Arrays.sort(indices, Comparator.comparingInt(i -> finish[i]));
        for (int i : indices) {
            if (start[i] > finishtime) {
                finishtime = finish[i];
                ans++;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def activitySelection(self, start, finish):
        ans, finishtime = 0, -1
        for s, f in sorted(zip(start, finish), key=lambda x: x[1]):
            if s > finishtime: finishtime = f; ans += 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
