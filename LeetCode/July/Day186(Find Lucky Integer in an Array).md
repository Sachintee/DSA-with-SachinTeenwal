--- ❤️ ---

# 🚀 _Day 186. Find Lucky Integer in an Array_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-lucky-integer-in-an-array/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int findLucky(vector<int>& arr) {
        int cnt[501]{};
        for (int x : arr) {
            ++cnt[x];
        }
        for (int x = 500; x; --x) {
            if (x == cnt[x]) {
                return x;
            }
        }
        return -1;
    }
};
```

## Code (Java)

```java
class Solution {
    public int findLucky(int[] arr) {
        int[] cnt = new int[501];
        for (int x : arr) {
            ++cnt[x];
        }
        for (int x = cnt.length - 1; x > 0; --x) {
            if (x == cnt[x]) {
                return x;
            }
        }
        return -1;
    }
}
```

## Code (Python)

```python
class Solution:
    def findLucky(self, arr: List[int]) -> int:
        cnt = Counter(arr)
        return max((x for x, v in cnt.items() if x == v), default=-1)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
