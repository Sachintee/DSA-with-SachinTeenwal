

# 🚀 _Day 365. NEXTGREATER_


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/nextgreater/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> nextGreater(vector<int>& A) {
        int n = A.size();
        vector<int> res(n, -1);
        stack<int> st;

        for (int i = n - 1; i >= 0; i--) {
            while (!st.empty() && st.top() <= A[i])
                st.pop();

            if (!st.empty())
                res[i] = st.top();

            st.push(A[i]);
        }

        return res;
    }
};

```

## Code (Java)

```java
import java.util.*;

class Solution {
    public ArrayList<Integer> nextGreater(ArrayList<Integer> A) {
        int n = A.size();
        ArrayList<Integer> res = new ArrayList<>(Collections.nCopies(n, -1));
        Stack<Integer> st = new Stack<>();

        for (int i = n - 1; i >= 0; i--) {
            while (!st.isEmpty() && st.peek() <= A.get(i))
                st.pop();

            if (!st.isEmpty())
                res.set(i, st.peek());

            st.push(A.get(i));
        }

        return res;
    }
}

```

## Code (Python3)

```python
class Solution:
    def nextGreater(self, A):
        n = len(A)
        result = [-1] * n
        stack = []

        for i in range(n - 1, -1, -1):
            while stack and stack[-1] <= A[i]:
                stack.pop()

            if stack:
                result[i] = stack[-1]

            stack.append(A[i])

        return result

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
