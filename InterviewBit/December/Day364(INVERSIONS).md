

# 🚀 _Day 364. INVERSIONS_ 


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/inversions/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long mergeCount(vector<int>& a, int l, int m, int r) {
        vector<int> left(a.begin() + l, a.begin() + m + 1);
        vector<int> right(a.begin() + m + 1, a.begin() + r + 1);

        int i = 0, j = 0, k = l;
        long long inv = 0;

        while (i < left.size() && j < right.size()) {
            if (left[i] <= right[j]) {
                a[k++] = left[i++];
            } else {
                a[k++] = right[j++];
                inv += (left.size() - i);
            }
        }

        while (i < left.size()) a[k++] = left[i++];
        while (j < right.size()) a[k++] = right[j++];

        return inv;
    }

    long long mergeSort(vector<int>& a, int l, int r) {
        if (l >= r) return 0;
        int m = l + (r - l) / 2;
        long long inv = 0;
        inv += mergeSort(a, l, m);
        inv += mergeSort(a, m + 1, r);
        inv += mergeCount(a, l, m, r);
        return inv;
    }

    int countInversions(vector<int>& A) {
        return (int)mergeSort(A, 0, A.size() - 1);
    }
};

```

## Code (Java)

```java
class Solution {

    private long mergeCount(int[] a, int l, int m, int r) {
        int[] left = java.util.Arrays.copyOfRange(a, l, m + 1);
        int[] right = java.util.Arrays.copyOfRange(a, m + 1, r + 1);

        int i = 0, j = 0, k = l;
        long inv = 0;

        while (i < left.length && j < right.length) {
            if (left[i] <= right[j]) {
                a[k++] = left[i++];
            } else {
                a[k++] = right[j++];
                inv += (left.length - i);
            }
        }

        while (i < left.length) a[k++] = left[i++];
        while (j < right.length) a[k++] = right[j++];

        return inv;
    }

    private long mergeSort(int[] a, int l, int r) {
        if (l >= r) return 0;
        int m = l + (r - l) / 2;
        long inv = 0;
        inv += mergeSort(a, l, m);
        inv += mergeSort(a, m + 1, r);
        inv += mergeCount(a, l, m, r);
        return inv;
    }

    public int countInversions(int[] A) {
        return (int)mergeSort(A, 0, A.length - 1);
    }
}

```

## Code (Python3)

```python
class Solution:
    def countInversions(self, A):

        def merge_sort(arr):
            if len(arr) <= 1:
                return arr, 0

            mid = len(arr) // 2
            left, inv_left = merge_sort(arr[:mid])
            right, inv_right = merge_sort(arr[mid:])

            merged = []
            i = j = 0
            inv_count = inv_left + inv_right

            while i < len(left) and j < len(right):
                if left[i] <= right[j]:
                    merged.append(left[i])
                    i += 1
                else:
                    merged.append(right[j])
                    inv_count += len(left) - i
                    j += 1

            merged.extend(left[i:])
            merged.extend(right[j:])

            return merged, inv_count

        _, count = merge_sort(A)
        return count

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
