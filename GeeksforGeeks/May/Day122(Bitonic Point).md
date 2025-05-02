# *122. Bitonic Point*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximum-value-in-a-bitonic-array3001/1)

## **🧩 Problem Description**

Given an array `arr[]` of `n` elements that is first strictly increasing and then (optionally) strictly decreasing, return the **Bitonic Point** — the **maximum** element in the array.
It is guaranteed that the array contains **exactly one** bitonic point.


## Code(C++)
```cpp
class Solution {
  public:
    int findMaximum(vector<int> &arr) {
        int low = 0, high = arr.size() - 1;
        while (low < high) {
            int mid = (low + high) / 2;
            if (arr[mid] < arr[mid + 1])
                low = mid + 1;
            else
                high = mid;
        }
        return arr[low];
    }
};
```

## Code (Java)

```java
class Solution {
    public int findMaximum(int[] arr) {
        int low = 0, high = arr.length - 1;
        while (low < high) {
            int mid = (low + high) / 2;
            if (arr[mid] < arr[mid + 1])
                low = mid + 1;
            else
                high = mid;
        }
        return arr[low];
    }
}
```

## Code (Python)

```python
class Solution:
    def findMaximum(self, arr):
        low, high = 0, len(arr) - 1
        while low < high:
            mid = (low + high) // 2
            if arr[mid] < arr[mid + 1]:
                low = mid + 1
            else:
                high = mid
        return arr[low]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
