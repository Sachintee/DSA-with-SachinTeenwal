--- ❤️ ---

# 🚀 _Day 213. Max Product Subarray_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/max-product-subarray/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maxProduct(const vector<int> &A) {
        if (A.empty()) return 0;

        int maxProd = A[0];
        int maxEndingHere = A[0];
        int minEndingHere = A[0];

        for (int i = 1; i < A.size(); ++i) {
            int num = A[i];

            if (num < 0)
                swap(maxEndingHere, minEndingHere);

            maxEndingHere = max(num, num * maxEndingHere);
            minEndingHere = min(num, num * minEndingHere);

            maxProd = max(maxProd, maxEndingHere);
        }

        return maxProd;
    }
};

```

## Code (Java)

```java
public class Solution {
    public int maxProduct(final int[] A) {
        if (A.length == 0) return 0;

        int maxProd = A[0];
        int maxEndingHere = A[0];
        int minEndingHere = A[0];

        for (int i = 1; i < A.length; i++) {
            int num = A[i];

            if (num < 0) {
                int temp = maxEndingHere;
                maxEndingHere = minEndingHere;
                minEndingHere = temp;
            }

            maxEndingHere = Math.max(num, num * maxEndingHere);
            minEndingHere = Math.min(num, num * minEndingHere);

            maxProd = Math.max(maxProd, maxEndingHere);
        }

        return maxProd;
    }
}

```

## Code (Python3)

```python3
class Solution:
    # @param A : tuple of integers
    # @return an integer
    def maxProduct(self, A):
        if not A:
            return 0

        max_prod = A[0]
        max_ending_here = A[0]
        min_ending_here = A[0]

        for i in range(1, len(A)):
            num = A[i]

            if num < 0:
                # Swap because multiplying by a negative flips max/min
                max_ending_here, min_ending_here = min_ending_here, max_ending_here

            max_ending_here = max(num, num * max_ending_here)
            min_ending_here = min(num, num * min_ending_here)

            max_prod = max(max_prod, max_ending_here)

        return max_prod

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
