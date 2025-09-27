--- ❤️ ---

# 🚀 _Day 270. Largest Triangle Area_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/largest-triangle-area/description)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    double largestTriangleArea(vector<vector<int>>& points) {
        double ans = 0;
        for (auto& p1 : points) {
            int x1 = p1[0], y1 = p1[1];
            for (auto& p2 : points) {
                int x2 = p2[0], y2 = p2[1];
                for (auto& p3 : points) {
                    int x3 = p3[0], y3 = p3[1];
                    int u1 = x2 - x1, v1 = y2 - y1;
                    int u2 = x3 - x1, v2 = y3 - y1;
                    double t = abs(u1 * v2 - u2 * v1) / 2.0;
                    ans = max(ans, t);
                }
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public double largestTriangleArea(int[][] points) {
        double ans = 0;
        for (int[] p1 : points) {
            int x1 = p1[0], y1 = p1[1];
            for (int[] p2 : points) {
                int x2 = p2[0], y2 = p2[1];
                for (int[] p3 : points) {
                    int x3 = p3[0], y3 = p3[1];
                    int u1 = x2 - x1, v1 = y2 - y1;
                    int u2 = x3 - x1, v2 = y3 - y1;
                    double t = Math.abs(u1 * v2 - u2 * v1) / 2.0;
                    ans = Math.max(ans, t);
                }
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def largestTriangleArea(self, points: List[List[int]]) -> float:
        ans = 0
        for x1, y1 in points:
            for x2, y2 in points:
                for x3, y3 in points:
                    u1, v1 = x2 - x1, y2 - y1
                    u2, v2 = x3 - x1, y3 - y1
                    t = abs(u1 * v2 - u2 * v1) / 2
                    ans = max(ans, t)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
