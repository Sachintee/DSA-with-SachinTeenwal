--- ❤️ ---

# 🚀 _Day 115. Count of Interesting Subarrays_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-of-interesting-subarrays/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long countInterestingSubarrays(vector<int>& nums, int modulo, int k) {
        int n = nums.size();
        vector<int> arr(n);
        for (int i = 0; i < n; ++i) {
            arr[i] = int(nums[i] % modulo == k);
        }
        unordered_map<int, int> cnt;
        cnt[0] = 1;
        long long ans = 0;
        int s = 0;
        for (int x : arr) {
            s += x;
            ans += cnt[(s - k + modulo) % modulo];
            cnt[s % modulo]++;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public long countInterestingSubarrays(List<Integer> nums, int modulo, int k) {
        int n = nums.size();
        int[] arr = new int[n];
        for (int i = 0; i < n; ++i) {
            arr[i] = nums.get(i) % modulo == k ? 1 : 0;
        }
        Map<Integer, Integer> cnt = new HashMap<>();
        cnt.put(0, 1);
        long ans = 0;
        int s = 0;
        for (int x : arr) {
            s += x;
            ans += cnt.getOrDefault((s - k + modulo) % modulo, 0);
            cnt.merge(s % modulo, 1, Integer::sum);
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def countInterestingSubarrays(self, nums: List[int], modulo: int, k: int) -> int:
        arr = [int(x % modulo == k) for x in nums]
        cnt = Counter()
        cnt[0] = 1
        ans = s = 0
        for x in arr:
            s += x
            ans += cnt[(s - k) % modulo]
            cnt[s % modulo] += 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
