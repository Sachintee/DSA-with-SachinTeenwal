--- ❤️ ---

# 🚀 _Day 362. Kth Smallest Element in the Array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/kth-smallest-element-in-the-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
int Solution::kthsmallest(const vector<int> &A, int B) {
    int low = *min_element(A.begin(), A.end());
    int high = *max_element(A.begin(), A.end());

    while (low < high) {
        int mid = low + (high - low) / 2;
        int count = 0;

        for (int x : A)
            if (x <= mid)
                count++;

        if (count < B)
            low = mid + 1;
        else
            high = mid;
    }
    return low;
}

```

## Code (Java)

```java
public class Solution {
    public int kthsmallest(final int[] A, int B) {
        int low = Integer.MAX_VALUE, high = Integer.MIN_VALUE;
        for (int x : A) {
            low = Math.min(low, x);
            high = Math.max(high, x);
        }

        while (low < high) {
            int mid = low + (high - low) / 2;
            int count = 0;

            for (int x : A)
                if (x <= mid)
                    count++;

            if (count < B)
                low = mid + 1;
            else
                high = mid;
        }
        return low;
    }
}

```

## Code (Python)

```python
class Solution:
    def kthsmallest(self, A, B):
        low, high = min(A), max(A)

        while low < high:
            mid = (low + high) // 2
            count = 0
            for x in A:
                if x <= mid:
                    count += 1

            if count < B:
                low = mid + 1
            else:
                high = mid

        return low

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
