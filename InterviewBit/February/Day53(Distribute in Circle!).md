--- ❤️ ---

# 🚀 _Day 53. Distribute in Circle!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/distribute-in-circle/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

class Solution {
public:
    int solve(int A, int B, int C) {
        // Calculate the position using (C + A - 1) % B
        int position = (C + A - 1) % B;
        // If position is 0, set it to B (since positions are 1-based)
        if (position == 0) {
            return B;
        }
        return position;
    }
};

int main() {
    Solution sol;
    cout << sol.solve(2, 5, 1) << endl; // Output: 2
    cout << sol.solve(8, 5, 2) << endl; // Output: 4
    return 0;
}
```

## Code (Java)

```java
public class Solution {
    public int solve(int A, int B, int C) {
        // Calculate the position using (C + A - 1) % B
        int position = (C + A - 1) % B;
        // If position is 0, set it to B (since positions are 1-based)
        if (position == 0) {
            return B;
        }
        return position;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        System.out.println(sol.solve(2, 5, 1)); // Output: 2
        System.out.println(sol.solve(8, 5, 2)); // Output: 4
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B, C):
        # Calculate the position using (C + A - 1) % B
        position = (C + A - 1) % B
        # If position is 0, set it to B (since positions are 1-based)
        if position == 0:
            return B
        return position
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
