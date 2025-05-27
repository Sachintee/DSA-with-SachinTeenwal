--- ❤️ ---

# 🚀 _Day 147. Divisible and Non-divisible Sums Difference_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/divisible-and-non-divisible-sums-difference/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int differenceOfSums(int n, int m) {
        int ans = 0;
        for (int i = 1; i <= n; ++i) {
            ans += i % m ? i : -i;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int differenceOfSums(int n, int m) {
        int ans = 0;
        for (int i = 1; i <= n; ++i) {
            ans += i % m == 0 ? -i : i;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def differenceOfSums(self, n: int, m: int) -> int:
        return sum(i if i % m else -i for i in range(1, n + 1))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
