--- ❤️ ---

# 🚀 _Day 154. Nearest Smaller Element_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/nearest-smaller-element/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <stack>

using namespace std;

vector<int> prevSmaller(vector<int> &A) {
    stack<int> s;
    vector<int> result;
    for (int num : A) {
        while (!s.empty() && s.top() >= num) {
            s.pop();
        }
        if (!s.empty()) {
            result.push_back(s.top());
        } else {
            result.push_back(-1);
        }
        s.push(num);
    }
    return result;
}
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public ArrayList<Integer> prevSmaller(ArrayList<Integer> A) {
        Stack<Integer> stack = new Stack<>();
        ArrayList<Integer> result = new ArrayList<>();
        for (int num : A) {
            while (!stack.isEmpty() && stack.peek() >= num) {
                stack.pop();
            }
            if (!stack.isEmpty()) {
                result.add(stack.peek());
            } else {
                result.add(-1);
            }
            stack.push(num);
        }
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return a list of integers
    def prevSmaller(self, A):
        stack = []
        result = []
        for num in A:
            while stack and stack[-1] >= num:
                stack.pop()
            if stack:
                result.append(stack[-1])
            else:
                result.append(-1)
            stack.append(num)
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
