--- ❤️ ---

# 🚀 _Day 67. Minimum Recolors to Get K Consecutive Black Blocks_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-recolors-to-get-k-consecutive-black-blocks/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minimumRecolors(string blocks, int k) {
        int cnt = count(blocks.begin(), blocks.begin() + k, 'W');
        int ans = cnt;
        for (int i = k; i < blocks.size(); ++i) {
            cnt += blocks[i] == 'W';
            cnt -= blocks[i - k] == 'W';
            ans = min(ans, cnt);
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minimumRecolors(String blocks, int k) {
        int cnt = 0;
        for (int i = 0; i < k; ++i) {
            cnt += blocks.charAt(i) == 'W' ? 1 : 0;
        }
        int ans = cnt;
        for (int i = k; i < blocks.length(); ++i) {
            cnt += blocks.charAt(i) == 'W' ? 1 : 0;
            cnt -= blocks.charAt(i - k) == 'W' ? 1 : 0;
            ans = Math.min(ans, cnt);
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def minimumRecolors(self, blocks: str, k: int) -> int:
        ans = cnt = blocks[:k].count('W')
        for i in range(k, len(blocks)):
            cnt += blocks[i] == 'W'
            cnt -= blocks[i - k] == 'W'
            ans = min(ans, cnt)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
