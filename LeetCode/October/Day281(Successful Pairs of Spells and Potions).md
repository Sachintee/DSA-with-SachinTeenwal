--- ❤️ ---

# 🚀 _Day 281. Successful Pairs of Spells and Potions_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/successful-pairs-of-spells-and-potions/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> successfulPairs(vector<int>& spells, vector<int>& potions, long long success) {
        ranges::sort(potions);
        const int m = potions.size();
        vector<int> ans;
        ans.reserve(spells.size());

        for (int v : spells) {
            auto it = ranges::lower_bound(potions, static_cast<double>(success) / v);
            ans.push_back(m - static_cast<int>(it - potions.begin()));
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] successfulPairs(int[] spells, int[] potions, long success) {
        Arrays.sort(potions);
        int n = spells.length, m = potions.length;
        int[] ans = new int[n];
        for (int i = 0; i < n; ++i) {
            int left = 0, right = m;
            while (left < right) {
                int mid = (left + right) >> 1;
                if ((long) spells[i] * potions[mid] >= success) {
                    right = mid;
                } else {
                    left = mid + 1;
                }
            }
            ans[i] = m - left;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def successfulPairs(
        self, spells: List[int], potions: List[int], success: int
    ) -> List[int]:
        potions.sort()
        m = len(potions)
        return [m - bisect_left(potions, success / v) for v in spells]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
