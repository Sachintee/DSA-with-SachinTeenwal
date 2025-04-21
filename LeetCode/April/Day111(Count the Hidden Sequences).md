--- ❤️ ---

# 🚀 _Day 111. Count the Hidden Sequences_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-the-hidden-sequences/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int numberOfArrays(vector<int>& differences, int lower, int upper) {
        long long x = 0, mi = 0, mx = 0;
        for (int d : differences) {
            x += d;
            mi = min(mi, x);
            mx = max(mx, x);
        }
        return max(upper - lower - (mx - mi) + 1, 0LL);
    }
};
```

## Code (Java)

```java
class Solution {
    public int numberOfArrays(int[] differences, int lower, int upper) {
        long x = 0, mi = 0, mx = 0;
        for (int d : differences) {
            x += d;
            mi = Math.min(mi, x);
            mx = Math.max(mx, x);
        }
        return (int) Math.max(upper - lower - (mx - mi) + 1, 0);
    }
}
```

## Code (Python)

```python
class Solution:
    def numberOfArrays(self, differences: List[int], lower: int, upper: int) -> int:
        x = mi = mx = 0
        for d in differences:
            x += d
            mi = min(mi, x)
            mx = max(mx, x)
        return max(upper - lower - (mx - mi) + 1, 0)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
