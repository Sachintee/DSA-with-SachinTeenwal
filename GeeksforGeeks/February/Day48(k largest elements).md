---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Arrays
  - Sorting
  - Heap
---

# 🚀 _Day 48. K Largest Elements_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/heap-gfg-160/problem/k-largest-elements4206)  

## 💡 **Problem Description:**

Given an array `arr[]` of **positive integers** and an integer `k`, your task is to return the **k largest elements** in **decreasing order**.  


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> kLargest(vector<int>& arr, int k) {
        nth_element(arr.begin(), arr.end() - k, arr.end());
        partial_sort(arr.end() - k, arr.end(), arr.end(), greater<int>());
        return vector<int>(arr.end() - k, arr.end());
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> kLargest(int[] arr, int k) {
        Arrays.sort(arr);
        ArrayList<Integer> res = new ArrayList<>();
        for (int i = arr.length - 1; i >= arr.length - k; i--) res.add(arr[i]);
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def kLargest(self, arr, k):
        return sorted(arr, reverse=True)[:k]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
