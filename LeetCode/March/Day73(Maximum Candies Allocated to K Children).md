--- ❤️ ---

# 🚀 _Day 73. Maximum Candies Allocated to K Children_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-candies-allocated-to-k-children/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maximumCandies(vector<int>& candies, long long k) {
        int l = 0, r = ranges::max(candies);
        while (l < r) {
            int mid = (l + r + 1) >> 1;
            long long cnt = 0;
            for (int x : candies) {
                cnt += x / mid;
            }
            if (cnt >= k) {
                l = mid;
            } else {
                r = mid - 1;
            }
        }
        return l;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maximumCandies(int[] candies, long k) {
        int l = 0, r = Arrays.stream(candies).max().getAsInt();
        while (l < r) {
            int mid = (l + r + 1) >> 1;
            long cnt = 0;
            for (int x : candies) {
                cnt += x / mid;
            }
            if (cnt >= k) {
                l = mid;
            } else {
                r = mid - 1;
            }
        }
        return l;
    }
}
```

## Code (Python)

```python
class Solution:
    def maximumCandies(self, candies: List[int], k: int) -> int:
        l, r = 0, max(candies)
        while l < r:
            mid = (l + r + 1) >> 1
            if sum(x // mid for x in candies) >= k:
                l = mid
            else:
                r = mid - 1
        return l
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
