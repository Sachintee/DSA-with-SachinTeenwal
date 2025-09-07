--- ❤️ ---

# 🚀 _Day 250. Find N Unique Integers Sum up to Zero_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-n-unique-integers-sum-up-to-zero/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> sumZero(int n) {
        vector<int> ans(n);
        for (int i = 1, j = 0; i <= n / 2; ++i) {
            ans[j++] = i;
            ans[j++] = -i;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] sumZero(int n) {
        int[] ans = new int[n];
        for (int i = 1, j = 0; i <= n / 2; ++i) {
            ans[j++] = i;
            ans[j++] = -i;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def sumZero(self, n: int) -> List[int]:
        ans = []
        for i in range(n >> 1):
            ans.append(i + 1)
            ans.append(-(i + 1))
        if n & 1:
            ans.append(0)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
