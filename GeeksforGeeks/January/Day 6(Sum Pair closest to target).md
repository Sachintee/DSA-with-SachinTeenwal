---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - two-pointer-algorithm
  - Arrays
---

# 🚀 _Day 6. Sum Pair Closest to Target_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/two-pointer-technique-gfg-160/problem/pair-in-array-whose-sum-is-closest-to-x1124)

## 💡 **Problem Description:**

You are given an array `arr[]` and a number `target`. Your task is to find a pair of elements `(a, b)` in `arr[]` where `a <= b` whose sum is closest to the target. If there are multiple such pairs, return the pair with the maximum absolute difference. If no such pair exists, return an empty array.

## 🔍 **Example Walkthrough:**

**Input:**  
`arr[] = [10, 30, 20, 5], target = 25`  
**Output:**  
`[5, 20]`

**Input:**  
`arr[] = [5, 2, 7, 1, 4], target = 10`  
**Output:**  
`[2, 7]`  
Explanation: As both `(4, 7)` and `(2, 7)` are closest to the target 10, the absolute difference of `(2, 7)` is 5 and `(4, 7)` is 3. Hence, `[2, 7]` is the correct pair.

**Input:**  
`arr[] = [10], target = 10`  
**Output:**  
`[]`  
Explanation: The array contains only one element, so no valid pair can be formed.

### Constraints:
- $`1 <= arr.size() <= 2*10^5`$
- $`0 <= target <= 2*10^5`$
- $`0 <= arr[i] <= 10^5`$

## 🎯 **My Approach:**

1. **Sorting and Two-pointer Approach**:  
   - First, sort the array.
   - Use two pointers, `l` (left) and `r` (right), to traverse the array. Start by initializing `l` at the beginning and `r` at the end.
   - Calculate the sum of `arr[l]` and `arr[r]` and check how close it is to the target. Track the pair that gives the smallest difference.
   - Move the pointers based on whether the sum is less than or greater than the target, to attempt getting closer to the target.
   - If multiple pairs have the same sum, the one with the largest absolute difference should be returned.
   - Continue this process until the pointers meet.

## 🕒 **Time and Auxiliary Space Complexity** 

- **Expected Time Complexity:** O(n log n), where `n` is the number of elements in the array. This is because we need to sort the array, and sorting takes O(n log n) time. After sorting, the two-pointer traversal takes O(n) time.
- **Expected Auxiliary Space Complexity:** O(1), as we only use a constant amount of additional space (for the two pointers and result storage).

## 📝 **Solution Code**

## Code (C++)

```cpp
#include <vector>
#include <algorithm>
#include <cmath>

class Solution {
public:
    std::vector<int> sumClosest(std::vector<int>& arr, int target) {
        int n = arr.size();
        std::sort(arr.begin(), arr.end()); // Sort the array
        std::vector<int> res(2); // To store the result
        int minDiff = INT_MAX;

        int left = 0, right = n - 1;

        while (left < right) {
            int currSum = arr[left] + arr[right];

            // Update result if a closer sum is found
            if (std::abs(target - currSum) < minDiff) {
                minDiff = std::abs(target - currSum);
                res[0] = arr[left];
                res[1] = arr[right];
            }

            // Adjust pointers
            if (currSum < target) {
                left++;
            } else if (currSum > target) {
                right--;
            } else {
                return res; // Exact match found
            }
        }
        return res;
    }
};

```

## Code (Java)

```java
import java.util.Arrays;

class Solution {
    public int[] sumClosest(int[] arr, int target) {
        int n = arr.length;
        Arrays.sort(arr); // Sort the array
        int[] res = new int[2]; // To store the result
        int minDiff = Integer.MAX_VALUE;

        int left = 0;
        int right = n - 1;

        while (left < right) {
            int currSum = arr[left] + arr[right];

            // Update result if a closer sum is found
            if (Math.abs(target - currSum) < minDiff) {
                minDiff = Math.abs(target - currSum);
                res[0] = arr[left];
                res[1] = arr[right];
            }

            // Adjust pointers
            if (currSum < target) {
                left++;
            } else if (currSum > target) {
                right--;
            } else {
                return res; // Exact match found
            }
        }
        return res;
    }
}

```

## Code (Python)

```python
class Solution:
    def sumClosest(self, arr, target):
        # code here
        n = len(arr)
        arr.sort()
        res = []
        minDiff = float('inf')
    
        left = 0
        right = n - 1
    
        while left < right:
            currSum = arr[left] + arr[right]
    
            if abs(target - currSum) < minDiff:
                minDiff = abs(target - currSum)
                res = [arr[left], arr[right]]
    
            if currSum < target:
                left += 1
    
            elif currSum > target:
                right -= 1
    
            else:
                return res
    
        return res
          
```

## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal). Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
   <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>877</h4>
