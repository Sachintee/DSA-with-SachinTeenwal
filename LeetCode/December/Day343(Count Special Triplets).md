--- ❤️ ---

# 🚀 _Day 343. Count Special Triplets_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-special-triplets/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int specialTriplets(vector<int>& nums) {
        unordered_map<int, int> left, right;
        for (int x : nums) {
            right[x]++;
        }
        long long ans = 0;
        const int mod = 1e9 + 7;
        for (int x : nums) {
            right[x]--;
            ans = (ans + 1LL * left[x * 2] * right[x * 2] % mod) % mod;
            left[x]++;
        }
        return (int) ans;
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
