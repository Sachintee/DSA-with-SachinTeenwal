--- ❤️ ---

# 🚀 _Day 310. Ways To Tile A Floor_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/ways-to-tile-a-floor5836/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    int numberOfWays(int n) {
        if (n == 0 || n == 1) return 1;
        int a = 1, b = 1;
        for (int i = 2; i <= n; i++) {
            int c = a + b;
            a = b;
            b = c;
        }
        return b;
    }
};
```

## Code (Java)

```java
class Solution {
    public int numberOfWays(int n) {
        if (n == 0 || n == 1) return 1;
        int a = 1, b = 1;
        for (int i = 2; i <= n; i++) {
            int c = a + b;
            a = b;
            b = c;
        }
        return b;
    }
}
```

## Code (Python)

```python
class Solution:
    def numberOfWays(self, n: int) -> int:
        if n == 0 or n == 1:
            return 1
        a, b = 1, 1
        for _ in range(2, n + 1):
            a, b = b, a + b
        return b
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
