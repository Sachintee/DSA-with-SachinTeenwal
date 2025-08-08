---
title: "🕰️ Difference Check | GFG Solution 🔍"
keywords🏷️: ["⏰ minimum difference", "🔍 sorting", "📍 time parsing", "📈 array processing", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Minimum Time Difference problem: find minimum difference in seconds between any two time strings using efficient sorting technique. 🚀"
date: 📅 2025-08-07
---

# *219. Difference Check*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/difference-check/1)

## **🧩 Problem Description**

You are given an array `arr[]` of time strings in 24-hour clock format **"HH:MM:SS"**. Your task is to find the **minimum difference in seconds** between any two time strings in the array.

The clock wraps around at midnight, so the time difference between "23:59:59" and "00:00:00" is 1 second.


## Code(C++)
```cpp
class Solution {
public:
    int minDifference(vector<string>& arr) {
        vector<int> mins;
        for (auto& t : arr) {
            int h = (t[0] - '0') * 10 + (t[1] - '0');
            int m = (t[3] - '0') * 10 + (t[4] - '0');
            int s = (t[6] - '0') * 10 + (t[7] - '0');
            mins.push_back(h * 3600 + m * 60 + s);
        }
        sort(mins.begin(), mins.end());
        int res = mins[0] + 86400 - mins.back();
        for (int i = 1; i < mins.size(); i++) {
            res = min(res, mins[i] - mins[i-1]);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minDifference(String[] arr) {
        int[] mins = new int[arr.length];
        for (int i = 0; i < arr.length; i++) {
            String t = arr[i];
            int h = (t.charAt(0) - '0') * 10 + (t.charAt(1) - '0');
            int m = (t.charAt(3) - '0') * 10 + (t.charAt(4) - '0');
            int s = (t.charAt(6) - '0') * 10 + (t.charAt(7) - '0');
            mins[i] = h * 3600 + m * 60 + s;
        }
        Arrays.sort(mins);
        int res = mins[0] + 86400 - mins[mins.length - 1];
        for (int i = 1; i < mins.length; i++) {
            res = Math.min(res, mins[i] - mins[i - 1]);
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def minDifference(self, arr):
        mins = []
        for t in arr:
            h = int(t[:2])
            m = int(t[3:5])
            s = int(t[6:8])
            mins.append(h * 3600 + m * 60 + s)
        mins.sort()
        res = mins[0] + 86400 - mins[-1]
        for i in range(1, len(mins)):
            res = min(res, mins[i] - mins[i-1])
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
