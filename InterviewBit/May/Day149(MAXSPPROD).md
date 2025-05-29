--- ❤️ ---

# 🚀 _Day 149. MAXSPPROD_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/maxspprod/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <stack>
#include <algorithm>
using namespace std;

class Solution {
public:
    int maxSpecialProduct(vector<int>& A) {
        const int MOD = 1e9 + 7;
        int n = A.size();
        if (n < 3) return 0;
        
        vector<int> left(n, -1);
        vector<int> right(n, -1);
        stack<int> st;
        
        // Calculate Left Special Values
        for (int i = 0; i < n; ++i) {
            while (!st.empty() && A[st.top()] <= A[i]) {
                st.pop();
            }
            if (!st.empty()) {
                left[i] = st.top();
            }
            st.push(i);
        }
        
        while (!st.empty()) st.pop();
        
        // Calculate Right Special Values
        for (int i = n - 1; i >= 0; --i) {
            while (!st.empty() && A[st.top()] <= A[i]) {
                st.pop();
            }
            if (!st.empty()) {
                right[i] = st.top();
            }
            st.push(i);
        }
        
        long long max_product = 0;
        for (int i = 0; i < n; ++i) {
            if (left[i] != -1 && right[i] != -1) {
                long long product = (long long)left[i] * right[i];
                if (product > max_product) {
                    max_product = product;
                }
            }
        }
        
        return max_product % MOD;
    }
};
```

## Code (Java)

```java
import java.util.Stack;

public class Solution {
    public int maxSpecialProduct(int[] A) {
        final int MOD = 1000000007;
        int n = A.length;
        if (n < 3) return 0;
        
        int[] left = new int[n];
        int[] right = new int[n];
        Stack<Integer> stack = new Stack<>();
        
        // Calculate Left Special Values
        for (int i = 0; i < n; i++) {
            while (!stack.isEmpty() && A[stack.peek()] <= A[i]) {
                stack.pop();
            }
            if (!stack.isEmpty()) {
                left[i] = stack.peek();
            } else {
                left[i] = -1;
            }
            stack.push(i);
        }
        
        stack.clear();
        
        // Calculate Right Special Values
        for (int i = n - 1; i >= 0; i--) {
            while (!stack.isEmpty() && A[stack.peek()] <= A[i]) {
                stack.pop();
            }
            if (!stack.isEmpty()) {
                right[i] = stack.peek();
            } else {
                right[i] = -1;
            }
            stack.push(i);
        }
        
        long maxProduct = 0;
        for (int i = 0; i < n; i++) {
            if (left[i] != -1 && right[i] != -1) {
                long product = (long)left[i] * right[i];
                if (product > maxProduct) {
                    maxProduct = product;
                }
            }
        }
        
        return (int)(maxProduct % MOD);
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return an integer
    def maxSpecialProduct(self, A):
        MOD = 10**9 + 7
        n = len(A)
        if n < 3:
            return 0
        
        left = [0] * n
        right = [0] * n
        stack = []
        
        # Calculate Left Special Values
        for i in range(n):
            while stack and A[stack[-1]] <= A[i]:
                stack.pop()
            if stack:
                left[i] = stack[-1]
            else:
                left[i] = -1
            stack.append(i)
        
        stack = []
        # Calculate Right Special Values
        for i in range(n-1, -1, -1):
            while stack and A[stack[-1]] <= A[i]:
                stack.pop()
            if stack:
                right[i] = stack[-1]
            else:
                right[i] = -1
            stack.append(i)
        
        max_product = 0
        for i in range(n):
            if left[i] != -1 and right[i] != -1:
                product = left[i] * right[i]
                if product > max_product:
                    max_product = product
        
        return max_product % MOD
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
