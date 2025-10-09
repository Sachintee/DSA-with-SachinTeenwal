--- ❤️ ---

# 🚀 _Day 282. Find the Minimum Amount of Time to Brew Potions_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-the-minimum-amount-of-time-to-brew-potions/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long minTime(vector<int>& skill, vector<int>& mana) {
        int n = skill.size();
        vector<long long> f(n);
        for (int x : mana) {
            long long tot = 0;
            for (int i = 0; i < n; ++i) {
                tot = max(tot, f[i]) + 1LL * skill[i] * x;
            }
            f[n - 1] = tot;
            for (int i = n - 2; i >= 0; --i) {
                f[i] = f[i + 1] - 1LL * skill[i + 1] * x;
            }
        }
        return f[n - 1];
    }
};
```

## Code (Java)

```java
class Solution {
    public long minTime(int[] skill, int[] mana) {
        int n = skill.length;
        long[] f = new long[n];
        for (int x : mana) {
            long tot = 0;
            for (int i = 0; i < n; ++i) {
                tot = Math.max(tot, f[i]) + skill[i] * x;
            }
            f[n - 1] = tot;
            for (int i = n - 2; i >= 0; --i) {
                f[i] = f[i + 1] - skill[i + 1] * x;
            }
        }
        return f[n - 1];
    }
}
```

## Code (Python)

```python
class Solution:
    def minTime(self, skill: List[int], mana: List[int]) -> int:
        max = lambda a, b: a if a > b else b
        n = len(skill)
        f = [0] * n
        for x in mana:
            tot = 0
            for i in range(n):
                tot = max(tot, f[i]) + skill[i] * x
            f[-1] = tot
            for i in range(n - 2, -1, -1):
                f[i] = f[i + 1] - skill[i + 1] * x
        return f[-1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
