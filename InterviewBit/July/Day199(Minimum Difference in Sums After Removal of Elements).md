--- ❤️ ---

# 🚀 _Day 199. Minimum Difference in Sums After Removal of Elements_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-difference-in-sums-after-removal-of-elements/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minimumDifference(vector<int>& nums) {
        int m = nums.size();
        int n = m / 3;

        vector<long long> pre(m + 1, 0);
        priority_queue<int> q1;
        long long s = 0;

        for (int i = 0; i < n * 2; ++i) {
            s += nums[i];
            q1.push(-nums[i]); // max heap with negative values as min heap

            if (q1.size() > n) {
                s += q1.top(); // subtract -x -> add x back
                q1.pop();
            }
            pre[i + 1] = s;
        }

        vector<long long> suf(m + 1, 0);
        priority_queue<int, vector<int>, greater<int>> q2;
        s = 0;

        for (int i = m; i > n; --i) {
            s += nums[i - 1];
            q2.push(nums[i - 1]);

            if (q2.size() > n) {
                s -= q2.top();
                q2.pop();
            }
            suf[i] = s;
        }

        long long ans = LLONG_MAX;
        for (int i = n; i <= n * 2; ++i) {
            ans = min(ans, pre[i] - suf[i + 1]);
        }

        return (int)ans;
    }
};

```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int minimumDifference(int[] nums) {
        int m = nums.length;
        int n = m / 3;

        long[] pre = new long[m + 1];
        PriorityQueue<Integer> q1 = new PriorityQueue<>(Collections.reverseOrder());
        long s = 0;

        for (int i = 0; i < n * 2; i++) {
            s += nums[i];
            q1.add(-nums[i]); // max heap with negative for min behaviour

            if (q1.size() > n) {
                s += q1.poll(); // subtract -x -> add x back
            }
            pre[i + 1] = s;
        }

        long[] suf = new long[m + 1];
        PriorityQueue<Integer> q2 = new PriorityQueue<>();
        s = 0;

        for (int i = m; i > n; i--) {
            s += nums[i - 1];
            q2.add(nums[i - 1]);

            if (q2.size() > n) {
                s -= q2.poll();
            }
            suf[i] = s;
        }

        long ans = Long.MAX_VALUE;
        for (int i = n; i <= n * 2; i++) {
            ans = Math.min(ans, pre[i] - suf[i + 1]);
        }

        return (int)ans;
    }
}

```

## Code (Python)

```python
class Solution:
    def minimumDifference(self, nums: List[int]) -> int:
        m = len(nums)
        n = m // 3

        s = 0
        pre = [0] * (m + 1)
        q1 = []
        for i, x in enumerate(nums[: n * 2], 1):
            s += x
            heappush(q1, -x)
            if len(q1) > n:
                s -= -heappop(q1)
            pre[i] = s

        s = 0
        suf = [0] * (m + 1)
        q2 = []
        for i in range(m, n, -1):
            x = nums[i - 1]
            s += x
            heappush(q2, x)
            if len(q2) > n:
                s -= heappop(q2)
            suf[i] = s

        return min(pre[i] - suf[i + 1] for i in range(n, n * 2 + 1))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
