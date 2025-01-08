
---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - two-pointer-algorithm
  - Arrays
  - Sorting
---

# 🚀 _Day 8. Count the number of possible triangles_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/two-pointer-technique-gfg-160/problem/count-possible-triangles-1587115620)



Please don't block our ads :( － Ad sponsors allow us to make Codeshare free.
Hide Ads
)

## 💡 **Problem Description:**

Given an integer array `arr[]`, find the number of triangles that can be formed with three different array elements as the lengths of three sides of the triangle.

A triangle with three given sides is only possible if the sum of any two sides is always greater than the third side.

## 🔍 **Example Walkthrough:**

Input:
```
arr[] = [4, 6, 3, 7]
```
Output:
```
3
```
Explanation: There are three triangles possible: [3, 4, 6], [4, 6, 7], and [3, 6, 7]. Note that [3, 4, 7] is not a possible triangle.

Input:
```
arr[] = [10, 21, 22, 100, 101, 200, 300]
```
Output:
```
6
```
Explanation: There can be 6 possible triangles: [10, 21, 22], [21, 100, 101], [22, 100, 101], [10, 100, 101], [100, 101, 200], and [101, 200, 300].

Input:
```
arr[] = [1, 2, 3]
```
Output:
```
0
```
Explanation: No triangles are possible.

### Constraints:
- $`3 <= arr.size() <= 10^3`$
- $`1 <= arr[i] <= 10^5`$



## 🎯 **My Approach:**

1. **Sorting the Array:**
   - Sort the array to make it easier to check if any three sides can form a valid triangle. Sorting ensures that we can always check for a valid triangle using the largest side as the third side.

2. **Iterating through the Array:**
   - After sorting the array, iterate over it in reverse order to check each possible triplet `(arr[i], arr[l], arr[r])` (with `l` and `r` starting from 0 and `i-1`, respectively).
   
3. **Checking Triangle Validity:**
   - For each triplet, if `arr[l] + arr[r] > arr[i]`, then the triplet can form a valid triangle. If this condition holds, increment the count of possible triangles.

4. **Returning the Result:**
   - The result is the final count of all valid triplets that form a triangle.


## 🕒 **Time and Auxiliary Space Complexity** 

- **Expected Time Complexity:** O(n^2), where `n` is the length of the array, as we iterate over the array and check pairs of elements for each element.
- **Expected Auxiliary Space Complexity:** O(1), since we only use a constant amount of additional space for counters and temporary variables.

## 📝 **Solution Code**

## Code (C++)

```cpp
#include <vector>
#include <algorithm>

class Solution {
public:
    int countTriangles(std::vector<int>& arr) {
        std::sort(arr.begin(), arr.end()); // Sort the array
        int n = arr.size();
        int count = 0;

        // Iterate from the last element downwards
        for (int i = n - 1; i >= 2; i--) {
            int left = 0, right = i - 1;

            while (left < right) {
                if (arr[left] + arr[right] > arr[i]) {
                    count += (right - left);
                    right--;
                } else {
                    left++;
                }
            }
        }
        return count;
    }
};
```

## Code (Java)

```java
import java.util.Arrays;

class Solution {
    public int countTriangles(int[] arr) {
        Arrays.sort(arr); // Sort the array
        int n = arr.length;
        int count = 0;

        // Iterate from the last element downwards
        for (int i = n - 1; i >= 2; i--) {
            int left = 0, right = i - 1;

            while (left < right) {
                if (arr[left] + arr[right] > arr[i]) {
                    count += (right - left);
                    right--;
                } else {
                    left++;
                }
            }
        }
        return count;
    }
}
```

## Code (Python)

```python
class Solution:
    def countTriangles(self, arr):
        arr.sort()
        n, count = len(arr), 0
        for i in range(n - 1, 1, -1):
            l, r = 0, i - 1
            while l < r:
                if arr[l] + arr[r] > arr[i]:
                    count += r - l
                    r -= 1
                else:
                    l += 1
        return count
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, please visit Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal). Thank you for your input; together, we strive to create a space where learning is a collaborative endeavor.

⭐ Star this repository if you find it helpful or intriguing! ⭐


---

<div align=center>
  <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>745</h4>