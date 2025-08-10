--- ❤️ ---

# 🚀 _Day 222. Reordered Power of 2_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/reordered-power-of-2/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    bool reorderedPowerOf2(int n) {
        string target = f(n);
        for (int i = 1; i <= 1000000000; i <<= 1) {
            if (target == f(i)) {
                return true;
            }
        }
        return false;
    }

private:
    string f(int x) {
        char cnt[10] = {};
        while (x > 0) {
            cnt[x % 10]++;
            x /= 10;
        }
        return string(cnt, cnt + 10);
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean reorderedPowerOf2(int n) {
        String target = f(n);
        for (int i = 1; i <= 1000000000; i <<= 1) {
            if (target.equals(f(i))) {
                return true;
            }
        }
        return false;
    }

    private String f(int x) {
        char[] cnt = new char[10];
        for (; x > 0; x /= 10) {
            cnt[x % 10]++;
        }
        return new String(cnt);
    }
}
```

## Code (Python)

```python
class Solution:
    def reorderedPowerOf2(self, n: int) -> bool:
        def f(x: int) -> List[int]:
            cnt = [0] * 10
            while x:
                x, v = divmod(x, 10)
                cnt[v] += 1
            return cnt

        target = f(n)
        i = 1
        while i <= 10**9:
            if f(i) == target:
                return True
            i <<= 1
        return False
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
