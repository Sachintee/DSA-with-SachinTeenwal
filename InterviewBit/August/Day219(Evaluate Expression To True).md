--- ❤️ ---

# 🚀 _Day 219. Evaluate Expression To True_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/evaluate-expression-to-true/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    const int MOD = 1003;
    unordered_map<string, int> memo;

    int countWays(string &A, int i, int j, bool isTrue) {
        if (i > j) return 0;
        if (i == j) {
            if (isTrue) return A[i] == 'T' ? 1 : 0;
            else return A[i] == 'F' ? 1 : 0;
        }

        string key = to_string(i) + "_" + to_string(j) + "_" + to_string(isTrue);
        if (memo.count(key)) return memo[key];

        int ways = 0;
        for (int k = i + 1; k < j; k += 2) {
            char op = A[k];

            int lt = countWays(A, i, k - 1, true);
            int lf = countWays(A, i, k - 1, false);
            int rt = countWays(A, k + 1, j, true);
            int rf = countWays(A, k + 1, j, false);

            if (op == '&') {
                if (isTrue) ways += lt * rt;
                else ways += lt * rf + lf * rt + lf * rf;
            } else if (op == '|') {
                if (isTrue) ways += lt * rt + lt * rf + lf * rt;
                else ways += lf * rf;
            } else if (op == '^') {
                if (isTrue) ways += lt * rf + lf * rt;
                else ways += lt * rt + lf * rf;
            }

            ways %= MOD;
        }

        memo[key] = ways;
        return ways;
    }

    int cnttrue(string A) {
        memo.clear();
        return countWays(A, 0, A.size() - 1, true);
    }
};

```

## Code (Java)

```java
import java.util.*;

public class Solution {
    final int MOD = 1003;
    Map<String, Integer> memo;

    public int cnttrue(String A) {
        memo = new HashMap<>();
        return countWays(A, 0, A.length() - 1, true);
    }

    private int countWays(String A, int i, int j, boolean isTrue) {
        if (i > j) return 0;
        if (i == j) {
            if (isTrue) return A.charAt(i) == 'T' ? 1 : 0;
            else return A.charAt(i) == 'F' ? 1 : 0;
        }

        String key = i + "_" + j + "_" + isTrue;
        if (memo.containsKey(key)) return memo.get(key);

        int ways = 0;
        for (int k = i + 1; k < j; k += 2) {
            char op = A.charAt(k);

            int lt = countWays(A, i, k - 1, true);
            int lf = countWays(A, i, k - 1, false);
            int rt = countWays(A, k + 1, j, true);
            int rf = countWays(A, k + 1, j, false);

            if (op == '&') {
                if (isTrue) ways += lt * rt;
                else ways += lt * rf + lf * rt + lf * rf;
            } else if (op == '|') {
                if (isTrue) ways += lt * rt + lt * rf + lf * rt;
                else ways += lf * rf;
            } else if (op == '^') {
                if (isTrue) ways += lt * rf + lf * rt;
                else ways += lt * rt + lf * rf;
            }

            ways %= MOD;
        }

        memo.put(key, ways);
        return ways;
    }
}

```

## Code (Python)

```python
class Solution:
    def cnttrue(self, A):
        MOD = 1003
        n = len(A)
        memo = {}

        def count(i, j, isTrue):
            if i > j:
                return 0
            if i == j:
                if isTrue:
                    return 1 if A[i] == 'T' else 0
                else:
                    return 1 if A[i] == 'F' else 0

            key = (i, j, isTrue)
            if key in memo:
                return memo[key]

            ways = 0
            for k in range(i + 1, j, 2):  # operator positions
                op = A[k]

                leftTrue = count(i, k - 1, 1)
                leftFalse = count(i, k - 1, 0)
                rightTrue = count(k + 1, j, 1)
                rightFalse = count(k + 1, j, 0)

                if op == '&':
                    if isTrue:
                        ways += leftTrue * rightTrue
                    else:
                        ways += (leftTrue * rightFalse + leftFalse * rightTrue + leftFalse * rightFalse)
                elif op == '|':
                    if isTrue:
                        ways += (leftTrue * rightTrue + leftTrue * rightFalse + leftFalse * rightTrue)
                    else:
                        ways += leftFalse * rightFalse
                elif op == '^':
                    if isTrue:
                        ways += (leftTrue * rightFalse + leftFalse * rightTrue)
                    else:
                        ways += (leftTrue * rightTrue + leftFalse * rightFalse)

                ways %= MOD

            memo[key] = ways
            return ways

        return count(0, n - 1, 1)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
