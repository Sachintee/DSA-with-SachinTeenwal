---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Arrays
  - Greedy
  - Sorting
  - Binary Search
---

# 🚀 _Day 86. Minimum Platforms_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/greedy-gfg-160/problem/minimum-platforms-1587115620)  

## 💡 **Problem Description:** 

You are given the arrival times `arr[]` and departure times `dep[]` of all trains that arrive at a railway station on the same day.  

Your task is to determine the **minimum number of platforms** required at the station to ensure that no train is kept waiting.  


## Code(C++)
```cpp
class Solution {
  public:
    int findPlatform(vector<int>& a, vector<int>& d) {
        sort(a.begin(), a.end());
        sort(d.begin(), d.end());
        int i = 0, j = 0, cnt = 0, ans = 0, n = a.size();
        while(i < n && j < n)
            a[i] <= d[j] ? (cnt++, ans = max(ans, cnt), i++) : (cnt--, j++);
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    static int findPlatform(int arr[], int dep[]) {
        Arrays.sort(arr);
        Arrays.sort(dep);
        int i = 0, j = 0, cnt = 0, ans = 0, n = arr.length;
        while(i < n && j < n)
            if(arr[i] <= dep[j]) { cnt++; ans = Math.max(ans, cnt); i++; }
            else { cnt--; j++; }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def minimumPlatform(self, arr, dep):
        arr.sort(); dep.sort()
        i = j = cnt = ans = 0
        n = len(arr)
        while i < n and j < n:
            if arr[i] <= dep[j]:
                cnt += 1; ans = max(ans, cnt); i += 1
            else:
                cnt -= 1; j += 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
