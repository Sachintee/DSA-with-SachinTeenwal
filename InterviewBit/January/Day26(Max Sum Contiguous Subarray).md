# 🚀 _Day 26. Max Sum Contiguous Subarray_ 🧠

Problem Description
Find the contiguous subarray within an array, A of length N which has the largest sum.

The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/max-sum-contiguous-subarray/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int currentSum = 0;
        int maxSum = INT_MIN; // To handle all negative numbers

        for (int num : nums) {
            currentSum = max(num, currentSum + num); // Extend the subarray or start a new one
            maxSum = max(maxSum, currentSum);       // Update the maximum sum
        }

        return maxSum;
    }
};

// Example usage
int main() {
    Solution solution;
    vector<int> A = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
    cout << "Maximum Sum: " << solution.maxSubArray(A) << endl; // Output: 6
    return 0;
}

```

## Code (Java)

```java
class Solution {
    public int maxSubArray(int[] nums) {
        int currentSum = 0;
        int maxSum = Integer.MIN_VALUE; // To handle all negative numbers

        for (int num : nums) {
            currentSum = Math.max(num, currentSum + num); // Extend the subarray or start a new one
            maxSum = Math.max(maxSum, currentSum);       // Update the maximum sum
        }

        return maxSum;
    }

    // Example usage
    public static void main(String[] args) {
        Solution solution = new Solution();
        int[] A = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
        System.out.println("Maximum Sum: " + solution.maxSubArray(A)); // Output: 6
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : tuple of integers
    # @return an integer
    def maxSubArray(self, A):
        # Initialize variables to store the current sum and maximum sum
        current_sum = 0
        max_sum = float('-inf')  # Negative infinity to handle all negative numbers
        
        for num in A:
            # Update the current sum by including the current number
            current_sum = max(num, current_sum + num)
            # Update the maximum sum if the current sum is greater
            max_sum = max(max_sum, current_sum)
        
        return max_sum

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>785</h4>
