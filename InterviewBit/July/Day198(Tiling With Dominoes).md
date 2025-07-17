--- ❤️ ---

# 🚀 _Day 198. Tiling With Dominoes_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/tiling-with-dominoes/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <iostream>

using namespace std;

const int MOD = 1e9 + 7;

int solve(int A) {
    if (A % 2 != 0) {
        return 0;
    }
    if (A == 0) {
        return 1;
    }
    if (A == 2) {
        return 3;
    }
    
    vector<int> dp(A + 1, 0);
    dp[0] = 1;
    dp[2] = 3;
    
    for (int i = 4; i <= A; i += 2) {
        dp[i] = (4LL * dp[i - 2] - dp[i - 4] + MOD) % MOD;
    }
    
    return dp[A];
}

int main() {
    int A;
    cin >> A;
    cout << solve(A) << endl;
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;

public class Solution {
    private static final int MOD = 1000000007;

    public int solve(int A) {
        if (A % 2 != 0) {
            return 0;
        }
        if (A == 0) {
            return 1;
        }
        if (A == 2) {
            return 3;
        }
        
        int[] dp = new int[A + 1];
        dp[0] = 1;
        dp[2] = 3;
        
        for (int i = 4; i <= A; i += 2) {
            dp[i] = (4 * dp[i - 2] - dp[i - 4] + MOD) % MOD;
        }
        
        return dp[A];
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int A = scanner.nextInt();
        Solution solution = new Solution();
        System.out.println(solution.solve(A));
        scanner.close();
    }
}
```

## Code (Python)

```python
MOD = 10**9 + 7

class Solution:
    # @param A : integer
    # @return an integer
    def solve(self, A):
        if A % 2 != 0:
            return 0
        if A == 0:
            return 1
        if A == 2:
            return 3
        
        dp = [0] * (A + 1)
        dp[0] = 1
        dp[2] = 3
        
        for i in range(4, A + 1, 2):
            dp[i] = (4 * dp[i - 2] - dp[i - 4]) % MOD
        
        return dp[A]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
