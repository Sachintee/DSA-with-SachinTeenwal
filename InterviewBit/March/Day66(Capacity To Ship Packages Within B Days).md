--- ❤️ ---

# 🚀 _Day 66. Capacity To Ship Packages Within B Days_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/capacity-to-ship-packages-within-b-days/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    Solution sol;
    vector<int> A = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    int B = 5;
    cout << sol.solve(A, B) << endl; // Output: 15

    A = {3, 2, 2, 4, 1, 4};
    B = 3;
    cout << sol.solve(A, B) << endl; // Output: 6
    return 0;
}
```

## Code (Java)

```java
public class Main {
    public static void main(String[] args) {
        Solution sol = new Solution();
        int[] A = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        int B = 5;
        System.out.println(sol.solve(A, B)); // Output: 15

        A = new int[]{3, 2, 2, 4, 1, 4};
        B = 3;
        System.out.println(sol.solve(A, B)); // Output: 6
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @param B : integer
    # @return an integer
    def solve(self, A, B):
        def is_possible(capacity):
            days = 1
            current_weight = 0
            for weight in A:
                if current_weight + weight > capacity:
                    days += 1
                    current_weight = 0
                current_weight += weight
            return days <= B

        left = max(A)  # Minimum possible capacity
        right = sum(A)  # Maximum possible capacity

        while left < right:
            mid = (left + right) // 2
            if is_possible(mid):
                right = mid
            else:
                left = mid + 1

        return left
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
