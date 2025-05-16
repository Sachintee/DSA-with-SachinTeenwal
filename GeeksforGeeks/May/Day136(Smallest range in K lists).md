# *136. Smallest Range in K Lists*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/find-smallest-range-containing-elements-from-k-lists/1)


## **🧩 Problem Description**

You are given a 2D integer array `arr[][]` of size `k × n`, where each row contains `n` sorted integers. Your task is to find the smallest range `[l, r]` that includes **at least one element from each of the `k` lists**.

If multiple such ranges exist, return the one that occurs first in the traversal.



## Code(C++)
```cpp
class Solution {
public:
    struct Node {
        int v, r, c;
        bool operator>(const Node& o) const { return v > o.v; }
    };
    vector<int> findSmallestRange(vector<vector<int>>& a) {
        int n = a.size(), m = a[0].size(), hi = INT_MIN, lo = 0, r = 1e9;
        priority_queue<Node, vector<Node>, greater<Node>> q;
        for (int i = 0; i < n; i++) q.push({a[i][0], i, 0}), hi = max(hi, a[i][0]);
        while (1) {
            auto x = q.top(); q.pop();
            if (hi - x.v < r - lo) lo = x.v, r = hi;
            if (x.c + 1 == m) break;
            int y = a[x.r][x.c + 1];
            q.push({y, x.r, x.c + 1});
            hi = max(hi, y);
        }
        return {lo, r};
    }
};
```

## Code (Java)

```java
class Solution {
    static class Node {
        int v, r, c;
        Node(int v, int r, int c) { this.v = v; this.r = r; this.c = c; }
    }
    public ArrayList<Integer> findSmallestRange(int[][] a) {
        int n = a.length, m = a[0].length, hi = Integer.MIN_VALUE, lo = 0, r = Integer.MAX_VALUE;
        PriorityQueue<Node> q = new PriorityQueue<>((x, y) -> x.v - y.v);
        for (int i = 0; i < n; i++) {
            q.add(new Node(a[i][0], i, 0));
            hi = Math.max(hi, a[i][0]);
        }
        while (true) {
            Node x = q.poll();
            if (hi - x.v < r - lo) { lo = x.v; r = hi; }
            if (x.c + 1 == m) break;
            int y = a[x.r][x.c + 1];
            q.add(new Node(y, x.r, x.c + 1));
            hi = Math.max(hi, y);
        }
        return new ArrayList<>(Arrays.asList(lo, r));
    }
}
```

## Code (Python)

```python
import heapq

class Solution:
    def findSmallestRange(self, a):
        n, m = len(a), len(a[0])
        hi = max(row[0] for row in a)
        q = [(a[i][0], i, 0) for i in range(n)]
        heapq.heapify(q)
        lo, r = 0, float('inf')
        while True:
            x, i, j = heapq.heappop(q)
            if hi - x < r - lo: lo, r = x, hi
            if j + 1 == m: break
            y = a[i][j + 1]
            heapq.heappush(q, (y, i, j + 1))
            hi = max(hi, y)
        return [lo, r]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
