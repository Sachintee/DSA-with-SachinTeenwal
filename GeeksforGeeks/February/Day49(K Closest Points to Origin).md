---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Sorting
  - Heap
  - Mathematical
  - priority-queue
  - Divide and Conquer
  - Geometric
  - Arrays
---

# 🚀 _Day 49. K Closest Points to Origin_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/heap-gfg-160/problem/k-closest-points-to-origin--172242)  

## 💡 **Problem Description:**

Given an array of points where each point is represented as **points[i] = [xi, yi]** on the **X-Y plane** and an integer **k**, return the **k closest points** to the origin **(0, 0)**.  


## Code(C++)
```cpp
class Solution {
    public:
        vector<vector<int>> kClosest(vector<vector<int>>& p, int k) {
                    nth_element(p.begin(), p.begin() + k, p.end(), [](auto&a, auto&b){
                                    return a[0]*a[0] + a[1]*a[1] < b[0]*b[0] + b[1]*b[1];
                    });
                            return {p.begin(), p.begin()+k};
        }
};
```

## Code (Java)

```java
class Solution {
    public int[][] kClosest(int[][] p, int k) {
        Arrays.sort(p, Comparator.comparingInt(a -> a[0] * a[0] + a[1] * a[1]));
        return Arrays.copyOfRange(p, 0, k);
    }
}
```

## Code (Python)

```python
class Solution:
    def kClosest(self, p: list[list[int]], k: int) -> list[list[int]]:
        return sorted(p, key=lambda a: a[0]**2 + a[1]**2)[:k]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
