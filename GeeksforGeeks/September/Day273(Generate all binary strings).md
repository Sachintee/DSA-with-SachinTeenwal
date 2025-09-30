---
title: "🔢 Generate All Binary Strings | GFG Solution 🔍"
keywords🏷️: ["🔢 binary strings", "🔍 bit manipulation", "📍 backtracking", "🔄 recursion", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Generate All Binary Strings problem: generate all possible binary strings of length n using bit manipulation, backtracking, and iterative techniques. 🚀"
date: 📅 2025-09-30
---

# *273. Generate All Binary Strings*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/generate-all-binary-strings/1)

## **🧩 Problem Description**

Given an integer `n`, you need to generate all the **binary strings** of `n` characters representing bits. Each position in the string can be either '0' or '1', resulting in 2^n possible combinations.

**Note:** Return the strings in ascending order.


## Code(C++)
```cpp
class Solution {
public:
    vector<string> binstr(int n) {
        vector<string> res;
        for (int i = 0; i < (1 << n); i++) {
            string s = "";
            for (int j = n - 1; j >= 0; j--) s += ((i >> j) & 1) ? '1' : '0';
            res.push_back(s);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int triangleNumber(int[] nums) {
        Arrays.sort(nums);
        int ans = 0;
        for (int i = 0, n = nums.length; i < n - 2; ++i) {
            for (int j = i + 1; j < n - 1; ++j) {
                int left = j + 1, right = n;
                while (left < right) {
                    int mid = (left + right) >> 1;
                    if (nums[mid] >= nums[i] + nums[j]) {
                        right = mid;
                    } else {
                        left = mid + 1;
                    }
                }
                ans += left - j - 1;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution {
public:
    int triangleNumber(vector<int>& nums) {
        ranges::sort(nums);
        int ans = 0, n = nums.size();
        for (int i = 0; i < n - 2; ++i) {
            for (int j = i + 1; j < n - 1; ++j) {
                int sum = nums[i] + nums[j];
                auto it = ranges::lower_bound(nums.begin() + j + 1, nums.end(), sum);
                int k = int(it - nums.begin()) - 1;
                ans += max(0, k - j);
            }
        }
        return ans;
    }
};
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
