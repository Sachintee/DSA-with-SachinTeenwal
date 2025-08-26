---
title: "🔢 Maximize Median After K Addition Operations | GFG Solution 🔍"
keywords🏷️: ["🔢 maximize median", "🔍 binary search", "📊 median optimization", "📈 greedy approach", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Maximize Median After K Addition Operations problem: find maximum possible median after performing at most k increment operations using binary search and greedy strategy. 🚀"
date: 📅 2025-08-25
---

# *237. Maximize Median After K Addition Operations*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximize-median-after-doing-k-addition-operation/1)

## **🧩 Problem Description**

You are given an array `arr[]` consisting of positive integers and an integer `k`. You are allowed to perform at most `k` operations, where in each operation, you can increment any one element of the array by 1. Determine the **maximum possible median** of the array that can be achieved after performing at most `k` such operations.

**Note:** The median of an array is defined as the middle element when the array (after sorting) has an odd size, or the average of the two middle elements when the array (after sorting) has an even size.


## Code(C++)
```cpp
class Solution {
public:
    bool canAchieve(vector<int>& arr, int target, int k) {
        int n = arr.size();
        long long ops = 0;
        
        if (n % 2 == 1) {
            for (int i = n/2; i < n; i++) {
                if (arr[i] < target) {
                    ops += target - arr[i];
                    if (ops > k) return false;
                }
            }
        } else {
            long long medianSum = arr[n/2-1] + arr[n/2];
            if (2LL * target > medianSum) {
                ops += 2LL * target - medianSum;
                if (ops > k) return false;
            }
            for (int i = n/2+1; i < n; i++) {
                if (arr[i] < target) {
                    ops += target - arr[i];
                    if (ops > k) return false;
                }
            }
        }
        return true;
    }
    
    int maximizeMedian(vector<int>& arr, int k) {
        sort(arr.begin(), arr.end());
        int n = arr.size();
        int l = (n % 2 == 1) ? arr[n/2] : (arr[n/2-1] + arr[n/2]) / 2;
        int r = l + k;
        int ans = l;
        
        while (l <= r) {
            int mid = l + (r - l) / 2;
            if (canAchieve(arr, mid, k)) {
                ans = mid;
                l = mid + 1;
            } else {
                r = mid - 1;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maximizeMedian(int[] arr, int k) {
        Arrays.sort(arr);
        int n = arr.length;
        int left = (n % 2 == 1) ? arr[n/2] : (arr[n/2-1] + arr[n/2]) / 2;
        int right = left + k;
        int result = left;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (canAchieve(arr, mid, k)) {
                result = mid;
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return result;
    }
    
    private boolean canAchieve(int[] arr, int target, int k) {
        int n = arr.length;
        long ops = 0;
        
        if (n % 2 == 1) {
            for (int i = n/2; i < n; i++) {
                if (arr[i] < target) {
                    ops += target - arr[i];
                    if (ops > k) return false;
                }
            }
        } else {
            long medianSum = (long)arr[n/2-1] + arr[n/2];
            if (2L * target > medianSum) {
                ops += 2L * target - medianSum;
                if (ops > k) return false;
            }
            for (int i = n/2+1; i < n; i++) {
                if (arr[i] < target) {
                    ops += target - arr[i];
                    if (ops > k) return false;
                }
            }
        }
        return true;
    }
}
```

## Code (Python)

```python
class Solution:
    def maximizeMedian(self, arr, k):
        arr.sort()
        n = len(arr)
        left = arr[n//2] if n % 2 == 1 else (arr[n//2-1] + arr[n//2]) // 2
        right = left + k
        result = left
        
        while left <= right:
            mid = left + (right - left) // 2
            if self.canAchieve(arr, mid, k):
                result = mid
                left = mid + 1
            else:
                right = mid - 1
        return result
    
    def canAchieve(self, arr, target, k):
        n = len(arr)
        ops = 0
        
        if n % 2 == 1:
            for i in range(n//2, n):
                if arr[i] < target:
                    ops += target - arr[i]
                    if ops > k:
                        return False
        else:
            median_sum = arr[n//2-1] + arr[n//2]
            if 2 * target > median_sum:
                ops += 2 * target - median_sum
                if ops > k:
                    return False
            for i in range(n//2+1, n):
                if arr[i] < target:
                    ops += target - arr[i]
                    if ops > k:
                        return False
        return True
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
