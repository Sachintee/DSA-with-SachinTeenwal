# *128. Missing Element of Arithmetic Progression*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/missing-element-of-ap2228/1)

## **🧩 Problem Description**

Given an array of `n` integers which forms an arithmetic progression (AP) except for one missing element, find the missing number in the array.

The given array is sorted in increasing order and follows the property:


## Code(C++)
```cpp
class Solution {
  public:
    int findMissing(vector<int> &arr) {
        int n = arr.size();
        int d1 = arr[1] - arr[0], 
            d2 = arr[n-1] - arr[n-2], 
            d3 = (arr[n-1] - arr[0]) / n;
        int d = (d1==d2 || d1==d3) ? d1 : d2;
        if (d == 0) return arr[0];
        int lo = 0, hi = n - 1;
        while (lo <= hi) {
            int mid = (lo + hi) >> 1;
            if ((arr[mid] - arr[0]) / d == mid) lo = mid + 1;
            else hi = mid - 1;
        }
        return arr[0] + lo * d;
    }
};
```

## Code (Java)

```java
class Solution {
    public int findMissing(int[] a) {
        int n = a.length;
        int d1 = a[1] - a[0], d2 = a[n-1] - a[n-2], d3 = (a[n-1] - a[0]) / n;
        int d = (d1==d2 || d1==d3) ? d1 : d2;
        if (d == 0) return a[0];
        int lo = 0, hi = n - 1;
        while (lo <= hi) {
            int mid = (lo + hi) >>> 1;
            if ((a[mid] - a[0]) / d == mid) lo = mid + 1;
            else hi = mid - 1;
        }
        return a[0] + lo * d;
    }
}
```

## Code (Python)

```python
class Solution:
    def findMissing(self, a):
        n = len(a)
        d1 = a[1] - a[0]; d2 = a[-1] - a[-2]; d3 = (a[-1] - a[0]) // n
        d = d1 if (d1==d2 or d1==d3) else d2
        if d == 0: return a[0]
        lo, hi = 0, n-1
        while lo <= hi:
            mid = (lo + hi) // 2
            if (a[mid]-a[0])//d == mid: lo = mid + 1
            else: hi = mid - 1
        return a[0] + lo * d
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
