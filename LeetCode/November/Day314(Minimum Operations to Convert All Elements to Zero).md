--- ❤️ ---

# 🚀 _Day 314. Minimum Operations to Convert All Elements to Zero_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-operations-to-convert-all-elements-to-zero/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minOperations(vector<int>& nums) {
        vector<int> stk;
        int ans = 0;
        for (int x : nums) {
            while (!stk.empty() && stk.back() > x) {
                ++ans;
                stk.pop_back();
            }
            if (x != 0 && (stk.empty() || stk.back() != x)) {
                stk.push_back(x);
            }
        }
        ans += stk.size();
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minOperations(int[] nums) {
        Deque<Integer> stk = new ArrayDeque<>();
        int ans = 0;
        for (int x : nums) {
            while (!stk.isEmpty() && stk.peek() > x) {
                ans++;
                stk.pop();
            }
            if (x != 0 && (stk.isEmpty() || stk.peek() != x)) {
                stk.push(x);
            }
        }
        ans += stk.size();
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def minOperations(self, nums: List[int]) -> int:
        stk = []
        ans = 0
        for x in nums:
            while stk and stk[-1] > x:
                ans += 1
                stk.pop()
            if x and (not stk or stk[-1] != x):
                stk.append(x)
        ans += len(stk)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
