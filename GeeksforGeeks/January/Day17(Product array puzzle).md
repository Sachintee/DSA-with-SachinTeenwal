---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - prefix-sum
  - Arrays
---

# 🚀 _Day 17. Product array puzzle_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/prefix-sum-gfg-160/problem/product-array-puzzle4525)

## 💡 **Problem Description:**

You are given an array `arr[]` of size `n`. Your task is to construct an array `res[]` such that `res[i]` is equal to the product of all the elements of `arr[]` except `arr[i]`. Return the resultant array `res[]`.  
**Note:** Each element in `res[]` lies within the 32-bit integer range.

## 🔍 **Example Walkthrough:**

**Input:**  
`arr[] = [10, 3, 5, 6, 2]`  
**Output:**  
`[180, 600, 360, 300, 900]`  
**Explanation:**  
For `i = 0`, `res[i] = 3 * 5 * 6 * 2 = 180`.  
For `i = 1`, `res[i] = 10 * 5 * 6 * 2 = 600`.  
For `i = 2`, `res[i] = 10 * 3 * 6 * 2 = 360`.  
For `i = 3`, `res[i] = 10 * 3 * 5 * 2 = 300`.  
For `i = 4`, `res[i] = 10 * 3 * 5 * 6 = 900`.



**Input:**  
`arr[] = [12, 0]`  
**Output:**  
`[0, 12]`  
**Explanation:**  
For `i = 0`, `res[i] = 0`.  
For `i = 1`, `res[i] = 12`.



### Constraints:
- $`2 <= arr.size() <= 10^5`$
- `-100 <= arr[i] <= 100`



## 🎯 **My Approach:**

1. **Handling Zeroes:**  
   If the array contains:
   - **More than one zero**: Every element in `res[]` will be `0`.
   - **Exactly one zero**: Only the position corresponding to the zero will have the product of all other non-zero elements, and the rest will be `0`.
   - **No zeroes**: Use the total product of all elements and divide by the current element for each position in the result array.

2. **Efficient Computation:**  
   - Iterate through the array once to calculate the total product of non-zero elements and the count of zeroes.
   - Build the result array in a second pass.



## 🕒 **Time and Auxiliary Space Complexity** 

- **Expected Time Complexity:** O(n), where `n` is the size of the array. The algorithm requires two linear traversals of the array.
- **Expected Auxiliary Space Complexity:** O(1), as the solution uses only a constant amount of additional space.

## 📝 **Solution Code**

## Code (C++)

```cpp
#include <vector>
using namespace std;

class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        int n = nums.size();
        vector<int> left_product(n, 1), result(n, 1);

        // Compute left product
        for (int i = 1; i < n; i++) {
            left_product[i] = left_product[i - 1] * nums[i - 1];
        }

        // Compute right product and final result
        int right_product_acc = 1;
        for (int i = n - 1; i >= 0; i--) {
            result[i] = left_product[i] * right_product_acc;
            right_product_acc *= nums[i];
        }

        return result;
    }
};
```



## Code (Java)

```java
import java.util.*;

class Solution {
    public int[] productExceptSelf(int[] nums) {
        int n = nums.length;
        int[] leftProduct = new int[n];
        int[] result = new int[n];

        // Initialize the first element of leftProduct to 1
        leftProduct[0] = 1;

        // Compute left product
        for (int i = 1; i < n; i++) {
            leftProduct[i] = leftProduct[i - 1] * nums[i - 1];
        }

        // Compute right product and final result
        int rightProductAcc = 1;
        for (int i = n - 1; i >= 0; i--) {
            result[i] = leftProduct[i] * rightProductAcc;
            rightProductAcc *= nums[i];
        }

        return result;
    }

    public static void main(String[] args) {
        Solution solution = new Solution();
        int[] nums = {1, 2, 3, 4};
        System.out.println(Arrays.toString(solution.productExceptSelf(nums)));
    }
}
```



## Code (Python)

```python
#User function Template for python3
class Solution:
    def productExceptSelf(self, nums):
        n = len(nums)
        left_product = [1] * n
        result = [1] * n
        for i in range(1, n):
            left_product[i] = left_product[i - 1] * nums[i - 1]
        right_product_acc = 1
        for i in range(n - 1, -1, -1):
            result[i] = left_product[i] * right_product_acc
            right_product_acc *= nums[i]

        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
   <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>955</h4>
