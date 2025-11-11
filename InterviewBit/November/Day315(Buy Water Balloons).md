--- ❤️ ---

# 🚀 _Day 315. Buy Water Balloons_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/buy-water-balloons/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    int solve(vector<int>& A, int B, int C) {
        sort(A.begin(), A.end());
        int n = A.size();

        auto canBuy = [&](int k) -> bool {
            long long total = 0;
            int idx = k - 1;
            while (idx >= 0) {
                total += A[idx];
                if (total > C) return false;
                idx -= B;
            }
            return total <= C;
        };

        int lo = 0, hi = n, ans = 0;
        while (lo <= hi) {
            int mid = (lo + hi) / 2;
            if (canBuy(mid)) {
                ans = mid;
                lo = mid + 1;
            } else {
                hi = mid - 1;
            }
        }
        return ans;
    }
};

int main() {
    Solution sol;
    vector<int> A = {2,4,5,3,7};
    cout << sol.solve(A, 2, 6) << "\n"; // -> 3
    return 0;
}

```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int solve(ArrayList<Integer> A, int B, int C) {
        Collections.sort(A);
        int n = A.size();

        // check if we can buy k balloons
        java.util.function.IntPredicate canBuy = (k) -> {
            long total = 0;
            int idx = k - 1;
            while (idx >= 0) {
                total += A.get(idx);
                if (total > C) return false;
                idx -= B;
            }
            return total <= C;
        };

        int lo = 0, hi = n, ans = 0;
        while (lo <= hi) {
            int mid = (lo + hi) / 2;
            if (canBuy.test(mid)) {
                ans = mid;
                lo = mid + 1;
            } else {
                hi = mid - 1;
            }
        }
        return ans;
    }

    // quick main for manual testing
    public static void main(String[] args) {
        Solution s = new Solution();
        ArrayList<Integer> A = new ArrayList<>(Arrays.asList(2,4,5,3,7));
        System.out.println(s.solve(A, 2, 6)); // -> 3
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @param B : integer
    # @param C : integer
    # @return an integer
    def solve(self, A, B, C):
        A.sort()
        n = len(A)

        def can_buy(k):
            # sum maxima of groups when picking k smallest items
            total = 0
            idx = k - 1
            while idx >= 0:
                total += A[idx]
                if total > C:
                    return False
                idx -= B
            return total <= C

        lo, hi = 0, n
        ans = 0
        while lo <= hi:
            mid = (lo + hi) // 2
            if can_buy(mid):
                ans = mid
                lo = mid + 1
            else:
                hi = mid - 1
        return ans

# Example quick test:
# print(Solution().solve([2,4,5,3,7], 2, 6))  # -> 3

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
