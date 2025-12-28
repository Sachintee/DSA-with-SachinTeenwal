--- ❤️ ---

# 🚀 _Day 362. Minimum time to fulfil all orders_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/minimum-time-to-fulfil-all-orders/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    bool canMake(vector<int>& ranks, int n, int time) {
        int total = 0;

        for (int r : ranks) {
            int t = 0;
            int k = 1;

            while (true) {
                t += r * k;
                if (t > time) break;
                total++;
                k++;
                if (total >= n) return true;
            }
        }
        return total >= n;
    }

    int minTime(vector<int>& ranks, int n) {
        int minRank = *min_element(ranks.begin(), ranks.end());

        int low = 0;
        int high = minRank * n * (n + 1) / 2;
        int ans = high;

        while (low <= high) {
            int mid = low + (high - low) / 2;

            if (canMake(ranks, n, mid)) {
                ans = mid;
                high = mid - 1;
            } else {
                low = mid + 1;
            }
        }
        return ans;
    }
};

```

## Code (Java)

```java
class Solution {
    private boolean canMake(int[] ranks, int n, int time) {
        int total = 0;
        for (int r : ranks) {
            int t = 0, k = 1;
            while (true) {
                t += r * k;
                if (t > time) break;
                total++;
                k++;
                if (total >= n) return true;
            }
        }
        return total >= n;
    }

    public int minTime(int[] ranks, int n) {
        int minRank = Integer.MAX_VALUE;
        for (int r : ranks) minRank = Math.min(minRank, r);

        int low = 0;
        int high = minRank * n * (n + 1) / 2;
        int ans = high;

        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (canMake(ranks, n, mid)) {
                ans = mid;
                high = mid - 1;
            } else {
                low = mid + 1;
            }
        }
        return ans;
    }
}

```

## Code (Python)

```python
class Solution:
    def minTime(self, ranks, n):
        def can_make(time):
            total = 0
            for r in ranks:
                t = 0
                k = 1
                while True:
                    t += r * k
                    if t > time:
                        break
                    total += 1
                    k += 1
                    if total >= n:
                        return True
            return total >= n

        min_rank = min(ranks)
        low, high = 0, min_rank * n * (n + 1) // 2
        ans = high

        while low <= high:
            mid = (low + high) // 2
            if can_make(mid):
                ans = mid
                high = mid - 1
            else:
                low = mid + 1

        return ans

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
