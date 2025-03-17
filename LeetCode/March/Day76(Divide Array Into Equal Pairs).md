--- ❤️ ---

# 🚀 _Day 76. Divide Array Into Equal Pairs_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/divide-array-into-equal-pairs/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    bool divideArray(vector<int>& nums) {
        int cnt[510]{};
        for (int x : nums) {
            ++cnt[x];
        }
        for (int i = 1; i <= 500; ++i) {
            if (cnt[i] % 2) {
                return false;
            }
        }
        return true;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean divideArray(int[] nums) {
        int[] cnt = new int[510];
        for (int v : nums) {
            ++cnt[v];
        }
        for (int v : cnt) {
            if (v % 2 != 0) {
                return false;
            }
        }
        return true;
    }
}
```

## Code (Python)

```python
class Solution:
    def divideArray(self, nums: List[int]) -> bool:
        cnt = Counter(nums)
        return all(v % 2 == 0 for v in cnt.values())
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
