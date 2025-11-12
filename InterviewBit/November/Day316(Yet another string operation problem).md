--- ❤️ ---

# 🚀 _Day 316. Yet another string operation problem_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/yet-another-string-operation-problem/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    int solve(string A, string B, int C) {
        int n = A.size();

        // Step 1: base cost (without any reverse)
        int base_cost = 0;
        for (int i = 0; i < n; i++) {
            if (A[i] != B[i]) base_cost++;
        }

        int min_cost = base_cost;

        // Step 2: try reversing any substring (i, j)
        for (int i = 0; i < n; i++) {
            for (int j = i; j < n; j++) {
                int cost = C;  // cost for one reverse
                for (int k = 0; k < n; k++) {
                    char newChar;
                    if (k >= i && k <= j) {
                        newChar = A[i + j - k];  // reversed part
                    } else {
                        newChar = A[k];
                    }
                    if (newChar != B[k]) cost++;
                }
                min_cost = min(min_cost, cost);
            }
        }

        return min_cost;
    }
};

int main() {
    Solution sol;
    cout << sol.solve("abceda", "bdecbo", 1) << endl;  // Output: 3
    cout << sol.solve("finger", "ginger", 0) << endl;  // Output: 1
    return 0;
}

```

## Code (Java)

```java
public class Solution {
    public int solve(String A, String B, int C) {
        int n = A.length();

        // Step 1: base cost (no reverse)
        int baseCost = 0;
        for (int i = 0; i < n; i++) {
            if (A.charAt(i) != B.charAt(i)) baseCost++;
        }

        int minCost = baseCost;

        // Step 2: try all substrings (i, j)
        for (int i = 0; i < n; i++) {
            for (int j = i; j < n; j++) {
                int cost = C; // cost for one reverse
                for (int k = 0; k < n; k++) {
                    char newChar;
                    if (k >= i && k <= j) {
                        newChar = A.charAt(i + j - k);
                    } else {
                        newChar = A.charAt(k);
                    }
                    if (newChar != B.charAt(k)) cost++;
                }
                minCost = Math.min(minCost, cost);
            }
        }

        return minCost;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        System.out.println(sol.solve("abceda", "bdecbo", 1)); // Output: 3
        System.out.println(sol.solve("finger", "ginger", 0)); // Output: 1
    }
}

```

## Code (Python)

```python
class Solution:
    def solve(self, A, B, C):
        n = len(A)

        # Step 1: base cost (no reverse)
        base_cost = sum(1 for i in range(n) if A[i] != B[i])
        min_cost = base_cost

        # Step 2: try all substrings for possible reverse
        for i in range(n):
            for j in range(i, n):
                cost = C  # cost for one reverse
                # after reversing A[i:j+1]
                for k in range(n):
                    # mapping index if reversed
                    if i <= k <= j:
                        new_char = A[i + j - k]
                    else:
                        new_char = A[k]

                    if new_char != B[k]:
                        cost += 1

                min_cost = min(min_cost, cost)

        return min_cost

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
