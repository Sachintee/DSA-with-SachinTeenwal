--- ❤️ ---

# 🚀 _Day 75. Minimum Time to Repair Cars_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-time-to-repair-cars/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long repairCars(vector<int>& ranks, int cars) {
        long long left = 0, right = 1LL * ranks[0] * cars * cars;
        while (left < right) {
            long long mid = (left + right) >> 1;
            long long cnt = 0;
            for (int r : ranks) {
                cnt += sqrt(mid / r);
            }
            if (cnt >= cars) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }
        return left;
    }
};
```

## Code (Java)

```java
class Solution {
    public long repairCars(int[] ranks, int cars) {
        long left = 0, right = 1L * ranks[0] * cars * cars;
        while (left < right) {
            long mid = (left + right) >> 1;
            long cnt = 0;
            for (int r : ranks) {
                cnt += Math.sqrt(mid / r);
            }
            if (cnt >= cars) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }
        return left;
    }
}
```

## Code (Python)

```python
class Solution:
    def repairCars(self, ranks: List[int], cars: int) -> int:
        def check(t: int) -> bool:
            return sum(int(sqrt(t // r)) for r in ranks) >= cars

        return bisect_left(range(ranks[0] * cars * cars), True, key=check)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
