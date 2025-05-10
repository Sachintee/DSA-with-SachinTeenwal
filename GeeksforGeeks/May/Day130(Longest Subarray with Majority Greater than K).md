# *130. Longest Subarray With Majority Greater Than K*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/longest-subarray-with-majority-greater-than-k/1)

## **🧩 Problem Description**

Given an array `arr[]` of size `n` and an integer `k`, find the length of the **longest subarray** in which the count of elements **greater than** `k` is **strictly more** than the count of elements **less than or equal** to `k`.


## Code(C++)
```cpp
class Solution {
public:
    int longestSubarray(vector<int>& arr, int k) {
        unordered_map<int,int> firstIdx;
        int s = 0, res = 0;
        for (int i = 0; i < arr.size(); ++i) {
            s += (arr[i] > k ? 1 : -1);
            if (s > 0) {
                res = i + 1;
            } else {
                if (!firstIdx.count(s)) firstIdx[s] = i;
                if (firstIdx.count(s - 1))
                    res = max(res, i - firstIdx[s - 1]);
            }
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int longestSubarray(int[] arr, int k) {
        Map<Integer,Integer> firstIdx = new HashMap<>();
        int s = 0, res = 0;
        for (int i = 0; i < arr.length; i++) {
            s += arr[i] > k ? 1 : -1;
            if (s > 0) {
                res = i + 1;
            } else {
                firstIdx.putIfAbsent(s, i);
                if (firstIdx.containsKey(s - 1)) {
                    res = Math.max(res, i - firstIdx.get(s - 1));
                }
            }
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestSubarray(self, arr, k):
        first_idx = {}
        s = res = 0
        for i, val in enumerate(arr):
            s += 1 if val > k else -1
            if s > 0:
                res = i + 1
            else:
                first_idx.setdefault(s, i)
                if (s - 1) in first_idx:
                    res = max(res, i - first_idx[s - 1])
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
