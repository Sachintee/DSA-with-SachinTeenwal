---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Sorting
  - two-pointer-algorithm
  - Arrays
---

# 🚀 _Day 5. Count Pairs whose sum is less than target_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/two-pointer-technique-gfg-160/problem/count-pairs-whose-sum-is-less-than-target)

## 💡 **Problem Description:**

You are given an array `arr[]` of integers and a target integer. Your task is to find the number of pairs in the array whose sum is strictly less than the given target.


## 📝 **Solution Code**

## Code (C++)

```cpp
#include <vector>
#include <algorithm>

class Solution {
  public:
    int countPairs(vector<int> &arr, int target) {
        std::sort(arr.begin(), arr.end());
        int left = 0, right = arr.size() - 1, ans = 0;
        
        while (left < right) {
            if (arr[left] + arr[right] < target) {
                ans += (right - left);
                left++;
            } else {
                right--;
            }
            }
        return ans;
        }
};
```

## Code (Java)

```java
import java.util.Arrays;

class Solution {
    public int countPairs(int[] arr, int target) {
        Arrays.sort(arr);
        int left = 0, right = arr.length - 1, ans = 0;

        while (left < right) {
            if (arr[left] + arr[right] < target) {
                ans += (right - left);
                left++;
            } else {
                right--;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def countPairs(self, arr, target):
        arr.sort()
        left, right = 0, len(arr) - 1
        ans = 0

        while left < right:
            if arr[left] + arr[right] < target:
                ans += (right - left)
                left += 1
            else:
                right -= 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal). Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

 ---

<div align="center">
  <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>652</h4>
