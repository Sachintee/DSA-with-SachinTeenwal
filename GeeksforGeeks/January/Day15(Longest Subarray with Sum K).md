---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - prefix-sum
  - Arrays
  - Hash
  - Map
---

# 🚀 _Day 15. Longest Subarray with Sum K_ 🧠

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/prefix-sum-gfg-160/problem/longest-sub-array-with-sum-k0809)

## 💡 **Problem Description:**

Given an array `arr[]` containing integers and an integer `k`, your task is to find the length of the longest subarray where the sum of its elements is equal to the given value `k`. If there is no subarray with sum equal to `k`, return `0`.



## 🔍 **Example Walkthrough:**

### **Example 1**  
**Input:**  
`arr[] = [10, 5, 2, 7, 1, -10], k = 15`  
**Output:**  
`6`  
**Explanation:**  
Subarrays with sum `15` are `[5, 2, 7, 1]`, `[10, 5]`, and `[10, 5, 2, 7, 1, -10]`. The longest subarray has length `6`.



### **Example 2**  
**Input:**  
`arr[] = [-5, 8, -14, 2, 4, 12], k = -5`  
**Output:**  
`5`  
**Explanation:**  
Only subarray with sum `-5` is `[-5, 8, -14, 2, 4]` of length `5`.



### **Example 3**  
**Input:**  
`arr[] = [10, -10, 20, 30], k = 5`  
**Output:**  
`0`  
**Explanation:**  
No subarray with sum equal to `5` exists in `arr[]`.



## Constraints:
- $`1 ≤ arr.size() ≤ 10^5`$
- $`-10^4 ≤ arr[i] ≤ 10^4`$
- $`-10^9 ≤ k ≤ 10^9`$



## 🎯 **My Approach:**

1. **Hashmap-Based Sliding Window Algorithm**:  
   - Use a hashmap (`mp`) to store the prefix sum and the earliest index at which it occurs.
   - Traverse the array, maintaining a running sum (`sum`) of the elements.  
   - At each step, check:
     - If `sum == k`, the subarray starts from the beginning, so update the result as the current index + 1.
     - If `sum - k` exists in the hashmap, calculate the length of the subarray ending at the current index and update the result if it is longer than the previous maximum.
   - Store the current `sum` in the hashmap if it is not already present to maintain the earliest index of each prefix sum.

2. **Steps:**
   - Initialize a hashmap to store prefix sums and their earliest indices.
   - Traverse the array while calculating the prefix sum.
   - Use conditions to determine if a subarray with the required sum exists and update the result accordingly.
   - Return the maximum length.



## 🕒 **Time and Auxiliary Space Complexity** 

- **Expected Time Complexity:** O(n), where `n` is the size of the array. Each element is visited once, and hashmap operations are O(1).  
- **Expected Auxiliary Space Complexity:** O(n), as we use a hashmap to store the prefix sums.

## 📝 **Solution Code**

## Code (C++)

```cpp
#include <vector>
#include <unordered_map>
#include <limits>
#include <algorithm>

class Solution {
public:
    int longestSubarray(std::vector<int>& arr, int k) {
        int n = arr.size();
        std::unordered_map<int, std::vector<int>> prefixSums;
        prefixSums[0] = {-1};  // Initialize with sum 0 at index -1
        int currentSum = 0;
        int maxLength = std::numeric_limits<int>::min();

        for (int i = 0; i < n; ++i) {
            currentSum += arr[i];

            // Check if (currentSum - k) exists in the map
            if (prefixSums.find(currentSum - k) != prefixSums.end()) {
                for (int index : prefixSums[currentSum - k]) {
                    maxLength = std::max(maxLength, i - index);
                }
            }

            // Add the current prefix sum to the map
            prefixSums[currentSum].push_back(i);
        }

        return maxLength != std::numeric_limits<int>::min() ? maxLength : 0;
    }
};
```



## Code (Java)

```java
import java.util.*;

public class Solution {
    public int longestSubarray(int[] arr, int k) {
        int n = arr.length;
        Map<Integer, List<Integer>> prefixSums = new HashMap<>();
        prefixSums.put(0, new ArrayList<>(Arrays.asList(-1))); // Initialize with sum 0 at index -1
        int currentSum = 0;
        int maxLength = Integer.MIN_VALUE;

        for (int i = 0; i < n; i++) {
            currentSum += arr[i];

            // Check if (currentSum - k) exists in the map
            if (prefixSums.containsKey(currentSum - k)) {
                for (int index : prefixSums.get(currentSum - k)) {
                    maxLength = Math.max(maxLength, i - index);
                }
            }

            // Add the current prefix sum to the map
            prefixSums.computeIfAbsent(currentSum, key -> new ArrayList<>()).add(i);
        }

        return maxLength != Integer.MIN_VALUE ? maxLength : 0;
    }

    public static void main(String[] args) {
        Solution solution = new Solution();

        // Example 1
        int[] arr1 = {1, 2, 3, 4, 5};
        int k1 = 9;
        System.out.println(solution.longestSubarray(arr1, k1)); // Output: 2

        // Example 2
        int[] arr2 = {1, -1, 5, -2, 3};
        int k2 = 3;
        System.out.println(solution.longestSubarray(arr2, k2)); // Output: 4
    }
}
```



## Code (Python)

```python
import math
class Solution:
    def longestSubarray(self, arr, k):  
        n=len(arr)
        d={0:[-1]}
        summ=0
        maxi=-math.inf

        for i in range(n):
            summ+=arr[i]
            if summ-k in d:
                for j in  (d[summ-k]):
                    # print(i,j)
                    maxi=max(maxi,i-j)
        
            if summ in d:
                d[summ].append(i)
            else:
                d[summ]=[i]
    
        # print(d)

        if maxi!=-math.inf:
            return maxi
        return 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
   <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>587</h4>
