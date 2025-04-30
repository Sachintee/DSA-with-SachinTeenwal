--- ❤️ ---

# 🚀 _Day 120. Find Numbers with Even Number of Digits_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-numbers-with-even-number-of-digits/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int findNumbers(vector<int>& nums) {
        int ans = 0;
        for (int& x : nums) {
            ans += to_string(x).size() % 2 == 0;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int findNumbers(int[] nums) {
        int ans = 0;
        for (int x : nums) {
            if (String.valueOf(x).length() % 2 == 0) {
                ++ans;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def findNumbers(self, nums: List[int]) -> int:
        return sum(len(str(x)) % 2 == 0 for x in nums)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
