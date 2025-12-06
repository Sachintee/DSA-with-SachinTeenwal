--- ❤️ ---

# 🚀 _Day 339. Count Partitions with Even Sum Difference_ 🧠


The problem can be found at the following link: [Problem Link]()

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countPartitions(vector<int>& nums) {
        int l = 0, r = accumulate(nums.begin(), nums.end(), 0);
        int ans = 0;
        for (int i = 0; i < nums.size() - 1; ++i) {
            l += nums[i];
            r -= nums[i];
            if ((l - r) % 2 == 0) {
                ++ans;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
