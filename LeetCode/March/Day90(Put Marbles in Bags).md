--- ❤️ ---

# 🚀 _Day 90. Put Marbles in Bags_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/put-marbles-in-bags/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long putMarbles(vector<int>& weights, int k) {
        int n = weights.size();
        vector<int> arr(n - 1);
        for (int i = 0; i < n - 1; ++i) {
            arr[i] = weights[i] + weights[i + 1];
        }
        sort(arr.begin(), arr.end());
        long long ans = 0;
        for (int i = 0; i < k - 1; ++i) {
            ans -= arr[i];
            ans += arr[n - 2 - i];
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public long putMarbles(int[] weights, int k) {
        int n = weights.length;
        int[] arr = new int[n - 1];
        for (int i = 0; i < n - 1; ++i) {
            arr[i] = weights[i] + weights[i + 1];
        }
        Arrays.sort(arr);
        long ans = 0;
        for (int i = 0; i < k - 1; ++i) {
            ans -= arr[i];
            ans += arr[n - 2 - i];
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def putMarbles(self, weights: List[int], k: int) -> int:
        arr = sorted(a + b for a, b in pairwise(weights))
        return sum(arr[len(arr) - k + 1 :]) - sum(arr[: k - 1])
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
