---
title: "🔄 Maximum Circular Subarray Sum | GFG Solution 🎯"
keywords🏷️: ["🔄 circular array", "📈 kadane algorithm", "🔍 subarray sum", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
\description: "✅ GFG solution to the Maximum Circular Subarray Sum problem: find maximum subarray sum in circular array using Kadane's algorithm with circular optimization. 🚀"
date: 📅 2025-07-25
---

# *206. Maximum Circular Subarray Sum*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/max-circular-subarray-sum-1587115620/1)

## **🧩 Problem Description**

You are given a circular array `arr[]` of integers. Your task is to find the maximum possible sum of a **non-empty subarray**. In a circular array, the subarray can start at the end and wrap around to the beginning. Return the maximum non-empty subarray sum, considering both **non-wrapping** and **wrapping** cases.

A circular array means that the end of the array wraps around to the beginning, allowing subarrays to span across this boundary.


## Code(C++)
```cpp
class Solution {
public:
    int maxCircularSum(vector<int>& arr) {
        int n = arr.size();
        int maxKadane = kadane(arr);
        int totalSum = 0;
        for (int& x : arr) {
            totalSum += x;
            x = -x;
        }
        int maxCircular = totalSum + kadane(arr);
        return maxCircular == 0 ? maxKadane : max(maxKadane, maxCircular);
    }
private:
    int kadane(vector<int>& arr) {
        int maxSum = arr[0], currSum = arr[0];
        for (int i = 1; i < arr.size(); i++) {
            currSum = max(arr[i], currSum + arr[i]);
            maxSum = max(maxSum, currSum);
        }
        return maxSum;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxCircularSum(int arr[]) {
        int maxKadane = kadane(arr);
        int totalSum = 0;
        for (int i = 0; i < arr.length; i++) {
            totalSum += arr[i];
            arr[i] = -arr[i];
        }
        int maxCircular = totalSum + kadane(arr);
        for (int i = 0; i < arr.length; i++) {
            arr[i] = -arr[i];
        }
        return maxCircular == 0 ? maxKadane : Math.max(maxKadane, maxCircular);
    }
    
    private int kadane(int[] arr) {
        int maxSum = arr[0], currSum = arr[0];
        for (int i = 1; i < arr.length; i++) {
            currSum = Math.max(arr[i], currSum + arr[i]);
            maxSum = Math.max(maxSum, currSum);
        }
        return maxSum;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxCircularSum(self, arr):
        def kadane(a):
            max_sum = curr_sum = a[0]
            for i in range(1, len(a)):
                curr_sum = max(a[i], curr_sum + a[i])
                max_sum = max(max_sum, curr_sum)
            return max_sum
        
        max_kadane = kadane(arr)
        total_sum = sum(arr)
        for i in range(len(arr)):
            arr[i] = -arr[i]
        max_circular = total_sum + kadane(arr)
        for i in range(len(arr)):
            arr[i] = -arr[i]
        
        return max_kadane if max_circular == 0 else max(max_kadane, max_circular)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
