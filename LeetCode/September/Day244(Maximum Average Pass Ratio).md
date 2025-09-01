--- ❤️ ---

# 🚀 _Day 244. Maximum Average Pass Ratio_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-average-pass-ratio/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    double maxAverageRatio(vector<vector<int>>& classes, int extraStudents) {
        priority_queue<tuple<double, int, int>> pq;
        for (auto& e : classes) {
            int a = e[0], b = e[1];
            double x = (double) (a + 1) / (b + 1) - (double) a / b;
            pq.push({x, a, b});
        }
        while (extraStudents--) {
            auto [_, a, b] = pq.top();
            pq.pop();
            a++;
            b++;
            double x = (double) (a + 1) / (b + 1) - (double) a / b;
            pq.push({x, a, b});
        }
        double ans = 0;
        while (pq.size()) {
            auto [_, a, b] = pq.top();
            pq.pop();
            ans += (double) a / b;
        }
        return ans / classes.size();
    }
};
```

## Code (Java)

```java
class Solution {
    public double maxAverageRatio(int[][] classes, int extraStudents) {
        PriorityQueue<double[]> pq = new PriorityQueue<>((a, b) -> {
            double x = (a[0] + 1) / (a[1] + 1) - a[0] / a[1];
            double y = (b[0] + 1) / (b[1] + 1) - b[0] / b[1];
            return Double.compare(y, x);
        });
        for (var e : classes) {
            pq.offer(new double[] {e[0], e[1]});
        }
        while (extraStudents-- > 0) {
            var e = pq.poll();
            double a = e[0] + 1, b = e[1] + 1;
            pq.offer(new double[] {a, b});
        }
        double ans = 0;
        while (!pq.isEmpty()) {
            var e = pq.poll();
            ans += e[0] / e[1];
        }
        return ans / classes.length;
    }
}
```

## Code (Python3)

```python
class Solution:
    def maxAverageRatio(self, classes: List[List[int]], extraStudents: int) -> float:
        h = [(a / b - (a + 1) / (b + 1), a, b) for a, b in classes]
        heapify(h)
        for _ in range(extraStudents):
            _, a, b = heappop(h)
            a, b = a + 1, b + 1
            heappush(h, (a / b - (a + 1) / (b + 1), a, b))
        return sum(v[1] / v[2] for v in h) / len(classes)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
