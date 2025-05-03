--- ❤️ ---

# 🚀 _Day 123. Minimum Domino Rotations For Equal Row_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-domino-rotations-for-equal-row/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minDominoRotations(vector<int>& tops, vector<int>& bottoms) {
        int n = tops.size();
        auto f = [&](int x) {
            int cnt1 = 0, cnt2 = 0;
            for (int i = 0; i < n; ++i) {
                if (tops[i] != x && bottoms[i] != x) {
                    return n + 1;
                }
                cnt1 += tops[i] == x;
                cnt2 += bottoms[i] == x;
            }
            return n - max(cnt1, cnt2);
        };
        int ans = min(f(tops[0]), f(bottoms[0]));
        return ans > n ? -1 : ans;
    }
};
```

## Code (Java)

```java
class Solution {
    private int n;
    private int[] tops;
    private int[] bottoms;

    public int minDominoRotations(int[] tops, int[] bottoms) {
        n = tops.length;
        this.tops = tops;
        this.bottoms = bottoms;
        int ans = Math.min(f(tops[0]), f(bottoms[0]));
        return ans > n ? -1 : ans;
    }

    private int f(int x) {
        int cnt1 = 0, cnt2 = 0;
        for (int i = 0; i < n; ++i) {
            if (tops[i] != x && bottoms[i] != x) {
                return n + 1;
            }
            cnt1 += tops[i] == x ? 1 : 0;
            cnt2 += bottoms[i] == x ? 1 : 0;
        }
        return n - Math.max(cnt1, cnt2);
    }
}
```

## Code (Python)

```python
class Solution:
    def minDominoRotations(self, tops: List[int], bottoms: List[int]) -> int:
        def f(x: int) -> int:
            cnt1 = cnt2 = 0
            for a, b in zip(tops, bottoms):
                if x not in (a, b):
                    return inf
                cnt1 += a == x
                cnt2 += b == x
            return len(tops) - max(cnt1, cnt2)

        ans = min(f(tops[0]), f(bottoms[0]))
        return -1 if ans == inf else ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
