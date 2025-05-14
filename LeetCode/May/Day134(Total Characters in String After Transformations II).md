--- ❤️ ---

# 🚀 _Day 134. Total Characters in String After Transformations II_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/total-characters-in-string-after-transformations-ii/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    static constexpr int MOD = 1e9 + 7;
    static constexpr int M = 26;

    using Matrix = vector<vector<int>>;

    Matrix matmul(const Matrix& a, const Matrix& b) {
        int n = a.size(), p = b.size(), q = b[0].size();
        Matrix res(n, vector<int>(q, 0));
        for (int i = 0; i < n; ++i) {
            for (int k = 0; k < p; ++k) {
                if (a[i][k]) {
                    for (int j = 0; j < q; ++j) {
                        res[i][j] = (res[i][j] + 1LL * a[i][k] * b[k][j] % MOD) % MOD;
                    }
                }
            }
        }
        return res;
    }

    Matrix matpow(Matrix mat, int power) {
        Matrix res(M, vector<int>(M, 0));
        for (int i = 0; i < M; ++i) res[i][i] = 1;
        while (power) {
            if (power % 2) res = matmul(res, mat);
            mat = matmul(mat, mat);
            power /= 2;
        }
        return res;
    }

    int lengthAfterTransformations(string s, int t, vector<int>& nums) {
        vector<int> cnt(M, 0);
        for (char c : s) {
            cnt[c - 'a']++;
        }

        Matrix matrix(M, vector<int>(M, 0));
        for (int i = 0; i < M; ++i) {
            for (int j = 1; j <= nums[i]; ++j) {
                matrix[i][(i + j) % M] = 1;
            }
        }

        Matrix cntMat(1, vector<int>(M));
        for (int i = 0; i < M; ++i) cntMat[0][i] = cnt[i];

        Matrix factor = matpow(matrix, t);
        Matrix result = matmul(cntMat, factor);

        int ans = 0;
        for (int x : result[0]) {
            ans = (ans + x) % MOD;
        }

        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    private final int mod = (int) 1e9 + 7;

    public int lengthAfterTransformations(String s, int t, List<Integer> nums) {
        final int m = 26;

        int[] cnt = new int[m];
        for (char c : s.toCharArray()) {
            cnt[c - 'a']++;
        }

        int[][] matrix = new int[m][m];
        for (int i = 0; i < m; i++) {
            int num = nums.get(i);
            for (int j = 1; j <= num; j++) {
                matrix[i][(i + j) % m] = 1;
            }
        }

        int[][] factor = matpow(matrix, t, m);
        int[] result = vectorMatrixMultiply(cnt, factor);
        int ans = 0;
        for (int val : result) {
            ans = (ans + val) % mod;
        }
        return ans;
    }

    private int[][] matmul(int[][] a, int[][] b) {
        int n = a.length;
        int p = b.length;
        int q = b[0].length;
        int[][] res = new int[n][q];
        for (int i = 0; i < n; i++) {
            for (int k = 0; k < p; k++) {
                if (a[i][k] == 0) continue;
                for (int j = 0; j < q; j++) {
                    res[i][j] = (int) ((res[i][j] + 1L * a[i][k] * b[k][j]) % mod);
                }
            }
        }
        return res;
    }

    private int[][] matpow(int[][] mat, int power, int m) {
        int[][] res = new int[m][m];
        for (int i = 0; i < m; i++) {
            res[i][i] = 1;
        }
        while (power > 0) {
            if ((power & 1) != 0) {
                res = matmul(res, mat);
            }
            mat = matmul(mat, mat);
            power >>= 1;
        }
        return res;
    }

    private int[] vectorMatrixMultiply(int[] vector, int[][] matrix) {
        int n = matrix.length;
        int[] result = new int[n];
        for (int i = 0; i < n; i++) {
            long sum = 0;
            for (int j = 0; j < n; j++) {
                sum = (sum + 1L * vector[j] * matrix[j][i]) % mod;
            }
            result[i] = (int) sum;
        }
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    def lengthAfterTransformations(self, s: str, t: int, nums: List[int]) -> int:
        mod = 10**9 + 7
        m = 26

        cnt = [0] * m
        for c in s:
            cnt[ord(c) - ord("a")] += 1

        matrix = [[0] * m for _ in range(m)]
        for i, x in enumerate(nums):
            for j in range(1, x + 1):
                matrix[i][(i + j) % m] = 1

        def matmul(a: List[List[int]], b: List[List[int]]) -> List[List[int]]:
            n, p, q = len(a), len(b), len(b[0])
            res = [[0] * q for _ in range(n)]
            for i in range(n):
                for k in range(p):
                    if a[i][k]:
                        for j in range(q):
                            res[i][j] = (res[i][j] + a[i][k] * b[k][j]) % mod
            return res

        def matpow(mat: List[List[int]], power: int) -> List[List[int]]:
            res = [[int(i == j) for j in range(m)] for i in range(m)]
            while power:
                if power % 2:
                    res = matmul(res, mat)
                mat = matmul(mat, mat)
                power //= 2
            return res

        cnt = [cnt]
        factor = matpow(matrix, t)
        result = matmul(cnt, factor)[0]

        ans = sum(result) % mod
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
