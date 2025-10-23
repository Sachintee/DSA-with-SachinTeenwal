---
title: "🎯 K Closest Points to Origin | GFG Solution 📍"
keywords🏷️: ["🎯 k closest points", "📍 distance calculation", "🔄 nth_element", "⚡ quickselect", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the K Closest Points to Origin problem: find k nearest points to origin using efficient selection algorithms like nth_element, sorting, and heaps. 🚀"
date: 📅 2025-10-23
---

# *296. K Closest Points to Origin*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/k-closest-points-to-origin--172242/1)

## **🧩 Problem Description**

Given an integer `k` and an array of points `points[][]`, where each point is represented as `points[i] = [xi, yi]` on the X-Y plane, return the **k closest points** to the origin `(0, 0)`.

The distance between two points on the X-Y plane is the **Euclidean distance**, defined as:

**distance = sqrt((x2 - x1)² + (y2 - y1)²)**

You can return the k closest points in any order. The driver code will print them in sorted order. Test cases are generated such that there will be a unique answer.


## Code(C++)
```cpp
class Solution {
public:
    vector<vector<int>> kClosest(vector<vector<int>>& points, int k) {
        nth_element(points.begin(), points.begin() + k, points.end(),
            [](auto& a, auto& b) { return a[0]*a[0]+a[1]*a[1] < b[0]*b[0]+b[1]*b[1]; });
        return vector<vector<int>>(points.begin(), points.begin() + k);
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<ArrayList<Integer>> kClosest(int[][] points, int k) {
        Arrays.sort(points, (a, b) -> (a[0]*a[0] + a[1]*a[1]) - (b[0]*b[0] + b[1]*b[1]));
        ArrayList<ArrayList<Integer>> res = new ArrayList<>();
        for (int i = 0; i < k; i++)
            res.add(new ArrayList<>(Arrays.asList(points[i][0], points[i][1])));
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def kClosest(self, points, k):
        points.sort(key=lambda x: x[0]**2 + x[1]**2)
        return points[:k]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
