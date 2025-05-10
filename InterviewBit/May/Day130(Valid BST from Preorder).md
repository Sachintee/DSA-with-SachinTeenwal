--- ❤️ ---

# 🚀 _Day 130. Valid BST from Preorder_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/valid-bst-from-preorder/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <stack>
#include <unordered_set>

using namespace std;

class Solution {
public:
    int solve(vector<int> &A) {
        // Check for duplicates
        unordered_set<int> seen;
        for (int num : A) {
            if (seen.find(num) != seen.end()) {
                return 0;
            }
            seen.insert(num);
        }
        
        stack<int> st;
        int min_val = -1; // Represents the minimum value the next element must be greater than
        
        for (int num : A) {
            if (num < min_val) {
                return 0;
            }
            while (!st.empty() && num > st.top()) {
                min_val = st.top();
                st.pop();
            }
            st.push(num);
        }
        return 1;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int solve(ArrayList<Integer> A) {
        // Check for duplicates
        Set<Integer> seen = new HashSet<>();
        for (int num : A) {
            if (seen.contains(num)) {
                return 0;
            }
            seen.add(num);
        }
        
        Stack<Integer> stack = new Stack<>();
        int min_val = -1; // Represents the minimum value the next element must be greater than
        
        for (int num : A) {
            if (num < min_val) {
                return 0;
            }
            while (!stack.isEmpty() && num > stack.peek()) {
                min_val = stack.pop();
            }
            stack.push(num);
        }
        return 1;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return an integer
    def solve(self, A):
        # Check for duplicates in the preorder sequence
        if len(A) != len(set(A)):
            return 0
        
        stack = []
        min_val = -1  # Represents the minimum value the next element must be greater than
        
        for num in A:
            if num < min_val:
                return 0
            while stack and num > stack[-1]:
                min_val = stack.pop()
            stack.append(num)
        return 1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
