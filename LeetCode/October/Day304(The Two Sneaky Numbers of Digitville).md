--- ❤️ ---

# 🚀 _Day 304. The Two Sneaky Numbers of Digitville_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/the-two-sneaky-numbers-of-digitville/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> getSneakyNumbers(vector<int>& nums) {
        vector<int> ans;
        int cnt[100]{};
        for (int x : nums) {
            if (++cnt[x] == 2) {
                ans.push_back(x);
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] getSneakyNumbers(int[] nums) {
        int[] ans = new int[2];
        int[] cnt = new int[100];
        int k = 0;
        for (int x : nums) {
            if (++cnt[x] == 2) {
                ans[k++] = x;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def getSneakyNumbers(self, nums: List[int]) -> List[int]:
        cnt = Counter(nums)
        return [x for x, v in cnt.items() if v == 2]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
