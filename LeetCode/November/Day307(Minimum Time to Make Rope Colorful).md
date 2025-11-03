--- ❤️ ---

# 🚀 _Day 307. Minimum Time to Make Rope Colorful_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-time-to-make-rope-colorful/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minCost(string colors, vector<int>& neededTime) {
        int ans = 0;
        int n = colors.size();
        for (int i = 0, j = 0; i < n; i = j) {
            j = i;
            int s = 0, mx = 0;
            while (j < n && colors[j] == colors[i]) {
                s += neededTime[j];
                mx = max(mx, neededTime[j]);
                ++j;
            }
            if (j - i > 1) {
                ans += s - mx;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minCost(String colors, int[] neededTime) {
        int ans = 0;
        int n = neededTime.length;
        for (int i = 0, j = 0; i < n; i = j) {
            j = i;
            int s = 0, mx = 0;
            while (j < n && colors.charAt(j) == colors.charAt(i)) {
                s += neededTime[j];
                mx = Math.max(mx, neededTime[j]);
                ++j;
            }
            if (j - i > 1) {
                ans += s - mx;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def minCost(self, colors: str, neededTime: List[int]) -> int:
        ans = i = 0
        n = len(colors)
        while i < n:
            j = i
            s = mx = 0
            while j < n and colors[j] == colors[i]:
                s += neededTime[j]
                if mx < neededTime[j]:
                    mx = neededTime[j]
                j += 1
            if j - i > 1:
                ans += s - mx
            i = j
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
