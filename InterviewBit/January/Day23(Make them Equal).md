
# 🚀 _Day 23. Make them Equal_ 🧠

Problem Description

You are given an array A of length N. In one operation you can select an index i ( 1 <= i <= N ) and change A[i] to floor(A[i]/2). floor(x) is the largest integer not greater than x. 

We want to make all the elements of the array equal. Calculate the minimum number of operations needed to do so.

The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/make-them-equal/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    int solve(vector<int>& A) {
        int n = A.size();
        vector<unordered_set<int>> reachableValues(n);

        // Function to calculate reachable values for a number
        auto getReachableValues = [](int x) {
            unordered_set<int> values;
            while (x > 0) {
                values.insert(x);
                x /= 2;
            }
            return values;
        };

        // Populate reachable values for all elements in A
        for (int i = 0; i < n; i++) {
            reachableValues[i] = getReachableValues(A[i]);
        }

        // Find common values by taking intersection of all sets
        unordered_set<int> commonValues = reachableValues[0];
        for (int i = 1; i < n; i++) {
            unordered_set<int> temp;
            for (int val : commonValues) {
                if (reachableValues[i].count(val)) {
                    temp.insert(val);
                }
            }
            commonValues = temp;
        }

        if (commonValues.empty()) return -1; // No common value exists

        // Calculate minimum operations to make all elements equal to a target
        int minOperations = INT_MAX;
        for (int target : commonValues) {
            int currentOperations = 0;
            for (int num : A) {
                int operations = 0;
                while (num > target) {
                    num /= 2;
                    operations++;
                }
                if (num != target) {
                    operations = INT_MAX; // Invalid case
                }
                currentOperations += operations;
            }
            minOperations = min(minOperations, currentOperations);
        }

        return minOperations;
    }
};

int main() {
    Solution solution;
    vector<int> A = {3, 1, 1, 3};
    cout << solution.solve(A) << endl; // Output: 2
    return 0;
}
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(int[] A) {
        int n = A.length;

        // Function to calculate reachable values for a number
        Set<Integer> getReachableValues(int x) {
            Set<Integer> values = new HashSet<>();
            while (x > 0) {
                values.add(x);
                x /= 2;
            }
            return values;
        }

        // Populate reachable values for all elements in A
        List<Set<Integer>> reachableValues = new ArrayList<>();
        for (int num : A) {
            reachableValues.add(getReachableValues(num));
        }

        // Find common values by taking intersection of all sets
        Set<Integer> commonValues = reachableValues.get(0);
        for (int i = 1; i < n; i++) {
            commonValues.retainAll(reachableValues.get(i));
        }

        if (commonValues.isEmpty()) return -1; // No common value exists

        // Calculate minimum operations to make all elements equal to a target
        int minOperations = Integer.MAX_VALUE;
        for (int target : commonValues) {
            int currentOperations = 0;
            for (int num : A) {
                int operations = 0;
                while (num > target) {
                    num /= 2;
                    operations++;
                }
                if (num != target) {
                    operations = Integer.MAX_VALUE; // Invalid case
                }
                currentOperations += operations;
            }
            minOperations = Math.min(minOperations, currentOperations);
        }

        return minOperations;
    }

    public static void main(String[] args) {
        Solution solution = new Solution();
        int[] A = {3, 1, 1, 3};
        System.out.println(solution.solve(A)); // Output: 2
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return an integer
    def solve(self, A):
        # Set to store all reachable values for each element
        reachable_values = []

        # Function to get all values reachable by repeatedly dividing by 2
        def get_reachable_values(x):
            values = set()
            while x > 0:
                values.add(x)
                x //= 2
            return values

        # Collect reachable values for each element in A
        for num in A:
            reachable_values.append(get_reachable_values(num))
        
        # Find the intersection of all sets to get common values
        common_values = set.intersection(*reachable_values)
        
        # If no common value exists, we can't make them equal
        if not common_values:
            return -1
        
        # Find the minimum number of operations to make all elements equal
        min_operations = float('inf')
        for target in common_values:
            current_operations = 0
            for num in A:
                operations = 0
                while num > target:
                    num //= 2
                    operations += 1
                if num != target:
                    operations = float('inf')  # Invalid case
                current_operations += operations
            min_operations = min(min_operations, current_operations)
        
        return min_operations
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>963</h4>
