---
title: "🔄 All Unique Permutations of an Array | GFG Solution 🎯"
keywords🏷️: ["🔄 permutations", "🔍 backtracking", "📊 STL", "🎯 next_permutation", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the All Unique Permutations of an Array problem: generate all distinct permutations of an array that may contain duplicates using efficient algorithms. 🚀"
date: 📅 2025-10-01
---

# *274. All Unique Permutations of an Array*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/all-unique-permutations-of-an-array/1)

## **🧩 Problem Description**

You are given an array `arr[]` that may contain duplicates. Your task is to find all possible **distinct permutations** of the array in **sorted order**.

A permutation is a rearrangement of all elements of the array. Since the array may contain duplicate elements, some permutations might be identical. We need to generate only the unique permutations and return them in lexicographically sorted order.


## Code(C++)
```cpp
class Solution {
public:
    vector<vector<int>> uniquePerms(vector<int>& arr) {
        sort(arr.begin(), arr.end());
        vector<vector<int>> res;
        do {
            res.push_back(arr);
        } while (next_permutation(arr.begin(), arr.end()));
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public static ArrayList<ArrayList<Integer>> uniquePerms(int[] arr) {
        Arrays.sort(arr);
        ArrayList<ArrayList<Integer>> res = new ArrayList<>();
        do {
            ArrayList<Integer> perm = new ArrayList<>();
            for (int num : arr) perm.add(num);
            res.add(perm);
        } while (nextPermutation(arr));
        return res;
    }
    private static boolean nextPermutation(int[] nums) {
        int n = nums.length;
        int i = n - 2;
        while (i >= 0 && nums[i] >= nums[i + 1]) i--;
        if (i < 0) return false;
        int j = n - 1;
        while (nums[j] <= nums[i]) j--;
        swap(nums, i, j);
        reverse(nums, i + 1, n - 1);
        return true;
    }
    private static void swap(int[] nums, int i, int j) {
        int t = nums[i]; nums[i] = nums[j]; nums[j] = t;
    }
    private static void reverse(int[] nums, int i, int j) {
        while (i < j) swap(nums, i++, j--);
    }
}
```

## Code (Python)

```python
class Solution:
    def uniquePerms(self, arr):
        arr.sort()
        res = []
        def next_permutation(nums):
            n = len(nums)
            i = n - 2
            while i >= 0 and nums[i] >= nums[i + 1]:
                i -= 1
            if i < 0:
                return False
            j = n - 1
            while nums[j] <= nums[i]:
                j -= 1
            nums[i], nums[j] = nums[j], nums[i]
            nums[i + 1:] = reversed(nums[i + 1:])
            return True
        res.append(arr[:])
        while next_permutation(arr):
            res.append(arr[:])
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
