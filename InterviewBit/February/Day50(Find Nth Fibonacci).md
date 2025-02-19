--- ❤️ ---

# 🚀 _Day 50. Find Nth Fibonacci_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/find-nth-fibonacci/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;
#define MOD 1000000007

typedef vector<vector<long long>> matrix;

matrix mat_mult(matrix &A, matrix &B) {
    return {{(A[0][0] * B[0][0] + A[0][1] * B[1][0]) % MOD, (A[0][0] * B[0][1] + A[0][1] * B[1][1]) % MOD},
            {(A[1][0] * B[0][0] + A[1][1] * B[1][0]) % MOD, (A[1][0] * B[0][1] + A[1][1] * B[1][1]) % MOD}};
}

matrix mat_expo(matrix M, long long exp) {
    matrix res = {{1, 0}, {0, 1}};
    while (exp) {
        if (exp % 2)
            res = mat_mult(res, M);
        M = mat_mult(M, M);
        exp /= 2;
    }
    return res;
}

class Solution {
public:
    int solve(int A) {
        if (A == 1 || A == 2)
            return 1;
        
        matrix base = {{1, 1}, {1, 0}};
        matrix result = mat_expo(base, A - 1);
        
        return result[0][0];
    }
};

int main() {
    Solution sol;
    int A;
    cin >> A;
    cout << sol.solve(A) << endl;
    return 0;
}
```

## Code (Java)

```java
import java.util.*;

class Solution {
    static final int MOD = 1000000007;
    
    static long[][] matMult(long[][] A, long[][] B) {
        return new long[][]{
            {(A[0][0] * B[0][0] + A[0][1] * B[1][0]) % MOD, (A[0][0] * B[0][1] + A[0][1] * B[1][1]) % MOD},
            {(A[1][0] * B[0][0] + A[1][1] * B[1][0]) % MOD, (A[1][0] * B[0][1] + A[1][1] * B[1][1]) % MOD}
        };
    }
    
    static long[][] matExpo(long[][] M, long exp) {
        long[][] res = {{1, 0}, {0, 1}};
        while (exp > 0) {
            if (exp % 2 == 1)
                res = matMult(res, M);
            M = matMult(M, M);
            exp /= 2;
        }
        return res;
    }
    
    public int solve(int A) {
        if (A == 1 || A == 2)
            return 1;
        
        long[][] base = {{1, 1}, {1, 0}};
        long[][] result = matExpo(base, A - 1);
        
        return (int) result[0][0];
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int A = scanner.nextInt();
        Solution sol = new Solution();
        System.out.println(sol.solve(A));
        scanner.close();
    }
}

```

## Code (Python)

```python
class Solution:
    def solve(self, A: int) -> int:
        MOD = 10**9 + 7
        
        def mat_mult(A, B):
            return [[(A[0][0] * B[0][0] + A[0][1] * B[1][0]) % MOD, (A[0][0] * B[0][1] + A[0][1] * B[1][1]) % MOD],
                    [(A[1][0] * B[0][0] + A[1][1] * B[1][0]) % MOD, (A[1][0] * B[0][1] + A[1][1] * B[1][1]) % MOD]]
        
        def mat_expo(M, exp):
            res = [[1, 0], [0, 1]]
            while exp:
                if exp % 2:
                    res = mat_mult(res, M)
                M = mat_mult(M, M)
                exp //= 2
            return res
        
        if A == 1 or A == 2:
            return 1
        
        base = [[1, 1], [1, 0]]
        result = mat_expo(base, A - 1)
        
        return result[0][0]

if __name__ == "__main__":
    sol = Solution()
    A = int(input())
    print(sol.solve(A))

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
