--- ❤️ ---

# 🚀 _Day 211. Subset Sum Problem!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/subset-sum-problem/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int solve(vector<int> &A, int B) {
        vector<bool> dp(B + 1, false);
        dp[0] = true;

        for (int num : A) {
            for (int j = B; j >= num; --j) {
                if (dp[j - num]) {
                    dp[j] = true;
                }
            }
        }

        return dp[B] ? 1 : 0;
    }
};

```

## Code (Java)

```java
public class Solution {
    public int solve(int[] A, int B) {
        boolean[] dp = new boolean[B + 1];
        dp[0] = true;

        for (int num : A) {
            for (int j = B; j >= num; j--) {
                if (dp[j - num]) {
                    dp[j] = true;
                }
            }
        }

        return dp[B] ? 1 : 0;
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
        dp = [False] * (B + 1)
        dp[0] = True  # Empty subset makes sum 0

        for num in A:
            for j in range(B, num - 1, -1):
                if dp[j - num]:
                    dp[j] = True

        return 1 if dp[B] else 0

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
