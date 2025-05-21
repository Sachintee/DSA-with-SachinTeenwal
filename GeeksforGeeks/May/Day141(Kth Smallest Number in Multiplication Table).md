# *141. Kth Smallest Number in Multiplication Table*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/kth-smallest-number-in-multiplication-table/1)


## **🧩 Problem Description**

Given three integers `m`, `n`, and `k`, representing an `m × n` multiplication table (1-indexed), return the `k`th smallest element from it.
Each cell of the matrix is defined as:
    **`mat[i][j] = i × j`**

The multiplication table is filled in row-wise sorted and column-wise sorted order.


## Code(C++)
```cpp
class Solution {
  public:
    int kthSmallest(int m, int n, int k) {
        int l = 1, r = m * n;
        while (l < r) {
            int mid = (l + r) / 2, cnt = 0;
            for (int i = 1; i <= m; ++i) cnt += min(n, mid / i);
            cnt < k ? l = mid + 1 : r = mid;
        }
        return l;
    }
};
```

## Code (Java)

```java
class Solution {
    public int kthSmallest(int m, int n, int k) {
        int l = 1, r = m * n;
        while (l < r) {
            int mid = (l + r) / 2, cnt = 0;
            for (int i = 1; i <= m; i++) cnt += Math.min(n, mid / i);
            if (cnt < k) l = mid + 1;
            else r = mid;
        }
        return l;
    }
}
```

## Code (Python)

```python
class Solution(object):
    def kthSmallest(self, m, n, k):
        l, r = 1, m * n
        while l < r:
            mid = (l + r) // 2
            cnt = sum(min(n, mid // i) for i in range(1, m + 1))
            if cnt < k: l = mid + 1
            else: r = mid
        return l
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
