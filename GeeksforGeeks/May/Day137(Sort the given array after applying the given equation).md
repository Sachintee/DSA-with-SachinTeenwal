# *137. Sort the given array after applying the given equation*


The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/sort-the-given-array-after-applying-the-given-equation0304/1)


## **🧩 Problem Description**

Given a sorted array `arr[]` in ascending order and integers `A`, `B`, and `C`, apply the quadratic transformation `f(x) = A·x² + B·x + C` to each element of the array.
Then return the transformed array in sorted order.



## Code(C++)
```cpp
class Solution {
  public:
    vector<int> sortArray(vector<int> &arr, int A, int B, int C) {
        int n = arr.size(), l = 0, r = n - 1, i = A >= 0 ? n - 1 : 0;
        vector<int> res(n);
        auto f = [&](int x) { return A * x * x + B * x + C; };
        while (l <= r) {
            int lv = f(arr[l]), rv = f(arr[r]);
            if (A >= 0) res[i--] = lv > rv ? lv : rv, lv > rv ? ++l : --r;
            else res[i++] = lv < rv ? lv : rv, lv < rv ? ++l : --r;
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> sortArray(int[] arr, int A, int B, int C) {
        int n = arr.length, l = 0, r = n - 1, i = A >= 0 ? n - 1 : 0;
        ArrayList<Integer> res = new ArrayList<>(Collections.nCopies(n, 0));
        while (l <= r) {
            int lv = A * arr[l] * arr[l] + B * arr[l] + C;
            int rv = A * arr[r] * arr[r] + B * arr[r] + C;
            if (A >= 0) {
                res.set(i--, lv > rv ? lv : rv);
                if (lv > rv) l++; else r--;
            } else {
                res.set(i++, lv < rv ? lv : rv);
                if (lv < rv) l++; else r--;
            }
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def sortArray(self, arr, A, B, C):
        n, l, r, i = len(arr), 0, len(arr) - 1, len(arr) - 1 if A >= 0 else 0
        f = lambda x: A * x * x + B * x + C
        res = [0] * n
        while l <= r:
            lv, rv = f(arr[l]), f(arr[r])
            if A >= 0:
                res[i] = lv if lv > rv else rv
                i -= 1
                l += lv > rv
                r -= lv <= rv
            else:
                res[i] = lv if lv < rv else rv
                i += 1
                l += lv < rv
                r -= lv >= rv
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
