---
Difficulty: Hard  
Source: 160 Days of Problem Solving  
Tags:
  - two-pointer-algorithm
  - Arrays
  - Dynamic Programming
  - Stack
---

# 🚀 _Day 12. Trapping Rain Water_ 🧠

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/two-pointer-technique-gfg-160/problem/trapping-rain-water-1587115621)

## 💡 **Problem Description:**

You are given an array `arr[]` of size `n`, where `arr[i]` represents the height of blocks, and the width of each block is 1. Your task is to calculate how much water can be trapped between the blocks after rainfall.

## 🔍 **Example Walkthrough:**

**Input:**  
`arr[] = [3, 0, 1, 0, 4, 0, 2]`  
**Output:**  
`10`  
**Explanation:**  
Water trapped = 0 + 3 + 2 + 3 + 0 + 2 + 0 = **10 units**

<img src="https://github.com/user-attachments/assets/0e54aa0d-cfd0-4e8c-87b5-c8a3df9b854c" width="45%">

**Input:**  
`arr[] = [3, 0, 2, 0, 4]`  
**Output:**  
`7`  
**Explanation:**  
Water trapped = 0 + 3 + 1 + 3 + 0 = **7 units**

**Input:**  
`arr[] = [2, 1, 5, 3, 1, 0, 4]`  
**Output:**  
`9`  
**Explanation:**  
Water trapped = 0 + 1 + 0 + 1 + 3 + 4 + 0 = **9 units**

**Input:**  
`arr[] = [1, 2, 3, 4]`  
**Output:**  
`0`  
**Explanation:**  
No water can be trapped as there are no height bounds on both sides.



### Constraints:
- $`1 < arr.size() < 10^5`$
- $`0 < arr[i] < 10^3`$



## 🎯 **My Approach:**

The problem can be solved efficiently using the **two-pointer technique**. This avoids the need for additional arrays to store left and right maximum heights, making the solution both time and space efficient. The key idea is to calculate the water trapped at each index by determining the minimum of the maximum heights on the left and right sides.

### Algorithm:
1. Initialize two pointers: `l` (left) starting at index 0 and `r` (right) starting at the last index.
2. Maintain two variables, `lMax` and `rMax`, to track the maximum heights seen so far from the left and right sides, respectively.
3. Use the following rules:
   - If `arr[l]` is smaller, calculate the water trapped at `l` using `lMax`, update `lMax` if needed, and move the left pointer (`l`) one step right.
   - If `arr[r]` is smaller, calculate the water trapped at `r` using `rMax`, update `rMax` if needed, and move the right pointer (`r`) one step left.
4. Continue until the two pointers meet.
5. The total water trapped is the sum of all individual contributions.

## 🕒 **Time and Auxiliary Space Complexity** 

- **Expected Time Complexity:** O(n), as each element in the array is processed exactly once using the two-pointer approach.
- **Expected Auxiliary Space Complexity:** O(1), as no additional arrays or data structures are used, and only a constant amount of extra space is required for the pointers and variables.

## 📝 **Solution Code**

## Code (C++)

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    Solution sol;
    vector<int> arr = {3, 0, 0, 2, 0, 4};
    cout << sol.maxWater(arr) << endl; // Output: 10
    return 0;
}
```



## Code (Java)

```java
public class Main {
    public static void main(String[] args) {
        Solution sol = new Solution();
        int[] arr = {3, 0, 0, 2, 0, 4};
        System.out.println(sol.maxWater(arr)); // Output: 10
    }
}
```



## Code (Python)

```python
class Solution:
    def maxWater(self, arr):
        # code here
        n=len(arr)
        waterFill=0
        lmax,rmax=0,0
        st,end=0,n-1
        while st<end:
            if arr[st]<arr[end]:
                if arr[st]<lmax:
                    waterFill+=lmax-arr[st]
                else:
                    lmax=arr[st]
                st+=1
            else:
                if arr[end]<rmax:
                    waterFill+=rmax-arr[end]
                else:
                    rmax=arr[end]
                end-=1
        return waterFill
```


## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal). Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
   <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>642</h4>
