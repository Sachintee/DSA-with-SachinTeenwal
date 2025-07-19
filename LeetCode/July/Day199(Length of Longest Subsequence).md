--- ❤️ ---

# 🚀 _Day 199. Length of Longest Subsequence_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/length-of-longest-subsequence/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long minimumDifference(vector<int>& nums) {
        int m = nums.size();
        int n = m / 3;

        using ll = long long;
        ll s = 0;
        ll pre[m + 1];
        priority_queue<int> q1;
        for (int i = 1; i <= n * 2; ++i) {
            int x = nums[i - 1];
            s += x;
            q1.push(x);
            if (q1.size() > n) {
                s -= q1.top();
                q1.pop();
            }
            pre[i] = s;
        }
        s = 0;
        ll suf[m + 1];
        priority_queue<int, vector<int>, greater<int>> q2;
        for (int i = m; i > n; --i) {
            int x = nums[i - 1];
            s += x;
            q2.push(x);
            if (q2.size() > n) {
                s -= q2.top();
                q2.pop();
            }
            suf[i] = s;
        }
        ll ans = 1e18;
        for (int i = n; i <= n * 2; ++i) {
            ans = min(ans, pre[i] - suf[i + 1]);
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public long minimumDifference(int[] nums) {
        int m = nums.length;
        int n = m / 3;
        long s = 0;
        long[] pre = new long[m + 1];
        PriorityQueue<Integer> pq = new PriorityQueue<>((a, b) -> b - a);
        for (int i = 1; i <= n * 2; ++i) {
            int x = nums[i - 1];
            s += x;
            pq.offer(x);
            if (pq.size() > n) {
                s -= pq.poll();
            }
            pre[i] = s;
        }
        s = 0;
        long[] suf = new long[m + 1];
        pq = new PriorityQueue<>();
        for (int i = m; i > n; --i) {
            int x = nums[i - 1];
            s += x;
            pq.offer(x);
            if (pq.size() > n) {
                s -= pq.poll();
            }
            suf[i] = s;
        }
        long ans = 1L << 60;
        for (int i = n; i <= n * 2; ++i) {
            ans = Math.min(ans, pre[i] - suf[i + 1]);
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : tuple of integers
    # @return an integer
    def longestSubsequenceLength(self, A):
        n = len(A)
        if n == 0:
            return 0

        # LIS from left to right
        lis = [1] * n
        for i in range(n):
            for j in range(i):
                if A[j] < A[i]:
                    lis[i] = max(lis[i], lis[j] + 1)

        # LDS from right to left
        lds = [1] * n
        for i in range(n-1, -1, -1):
            for j in range(n-1, i, -1):
                if A[j] < A[i]:
                    lds[i] = max(lds[i], lds[j] + 1)

        # Combine LIS and LDS for each peak
        max_len = 0
        for i in range(n):
            max_len = max(max_len, lis[i] + lds[i] - 1)

        return max_len

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
