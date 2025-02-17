--- ❤️ ---

# 🚀 _Day 48. Letter Tile Possibilities_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/letter-tile-possibilities/description/?envType=daily-question&envId=2025-02-17)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int numTilePossibilities(string tiles) {
        int cnt[26]{};
        for (char c : tiles) {
            ++cnt[c - 'A'];
        }
        function<int(int* cnt)> dfs = [&](int* cnt) -> int {
            int res = 0;
            for (int i = 0; i < 26; ++i) {
                if (cnt[i] > 0) {
                    ++res;
                    --cnt[i];
                    res += dfs(cnt);
                    ++cnt[i];
                }
            }
            return res;
        };
        return dfs(cnt);
    }
};
```

## Code (Java)

```java
class Solution {
    public int numTilePossibilities(String tiles) {
        int[] cnt = new int[26];
        for (char c : tiles.toCharArray()) {
            ++cnt[c - 'A'];
        }
        return dfs(cnt);
    }

    private int dfs(int[] cnt) {
        int res = 0;
        for (int i = 0; i < cnt.length; ++i) {
            if (cnt[i] > 0) {
                ++res;
                --cnt[i];
                res += dfs(cnt);
                ++cnt[i];
            }
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def numTilePossibilities(self, tiles: str) -> int:
        def dfs(cnt: Counter) -> int:
            ans = 0
            for i, x in cnt.items():
                if x > 0:
                    ans += 1
                    cnt[i] -= 1
                    ans += dfs(cnt)
                    cnt[i] += 1
            return ans

        cnt = Counter(tiles)
        return dfs(cnt)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
