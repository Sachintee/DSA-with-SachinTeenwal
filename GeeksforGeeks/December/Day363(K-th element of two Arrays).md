

# 🚀 _Day 363. K-th element of two Arrays_ 


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/k-th-element-of-two-sorted-array1317/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int kthElement(vector<int> &a, vector<int> &b, int k) {
        int n = a.size(), m = b.size();

        // Always binary search on smaller array
        if (n > m)
            return kthElement(b, a, k);

        int low = max(0, k - m);
        int high = min(k, n);

        while (low <= high) {
            int cutA = (low + high) / 2;
            int cutB = k - cutA;

            int leftA  = (cutA == 0) ? INT_MIN : a[cutA - 1];
            int leftB  = (cutB == 0) ? INT_MIN : b[cutB - 1];
            int rightA = (cutA == n) ? INT_MAX : a[cutA];
            int rightB = (cutB == m) ? INT_MAX : b[cutB];

            if (leftA <= rightB && leftB <= rightA) {
                return max(leftA, leftB);
            }
            else if (leftA > rightB) {
                high = cutA - 1;
            }
            else {
                low = cutA + 1;
            }
        }

        return -1; // never reached
    }
};

```

## Code (Java)

```java
class Solution {
    public long kthElement(int[] a, int[] b, int k) {
        int n = a.length, m = b.length;

        // Binary search on smaller array
        if (n > m)
            return kthElement(b, a, k);

        int low = Math.max(0, k - m);
        int high = Math.min(k, n);

        while (low <= high) {
            int cutA = (low + high) / 2;
            int cutB = k - cutA;

            int leftA  = (cutA == 0) ? Integer.MIN_VALUE : a[cutA - 1];
            int leftB  = (cutB == 0) ? Integer.MIN_VALUE : b[cutB - 1];

            int rightA = (cutA == n) ? Integer.MAX_VALUE : a[cutA];
            int rightB = (cutB == m) ? Integer.MAX_VALUE : b[cutB];

            if (leftA <= rightB && leftB <= rightA) {
                return Math.max(leftA, leftB);
            }
            else if (leftA > rightB) {
                high = cutA - 1;
            }
            else {
                low = cutA + 1;
            }
        }

        return -1; // never reached
    }
}

```

## Code (Python)

```python
class Solution:
    def kthElement(self, a, b, k):
        n, m = len(a), len(b)

        # Always binary search on smaller array
        if n > m:
            return self.kthElement(b, a, k)

        low = max(0, k - m)
        high = min(k, n)

        while low <= high:
            cutA = (low + high) // 2
            cutB = k - cutA

            leftA = a[cutA - 1] if cutA > 0 else float('-inf')
            leftB = b[cutB - 1] if cutB > 0 else float('-inf')

            rightA = a[cutA] if cutA < n else float('inf')
            rightB = b[cutB] if cutB < m else float('inf')

            if leftA <= rightB and leftB <= rightA:
                return max(leftA, leftB)
            elif leftA > rightB:
                high = cutA - 1
            else:
                low = cutA + 1

        return -1  # never reached

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
