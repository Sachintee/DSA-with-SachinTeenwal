# *125. Search in an Almost Sorted Array*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/search-in-an-almost-sorted-array/1)

## **🧩 Problem Description**

Given a sorted integer array `arr[]` consisting of distinct elements, where some elements of the array are moved to either of the adjacent positions, i.e. `arr[i]` may be present at `arr[i-1]` or `arr[i+1]`.
Given an integer `target`. You have to return the index (0-based) of the target in the array. If `target` is not present return -1.


## Code(C++)
```cpp
class Solution {
  public:
    int findTarget(vector<int>& arr, int target) {
        for(int i = 0; i < arr.size(); ++i)
            if(arr[i] == target) return i;
        return -1;
    }
};
```

## Code (Java)

```java
class Solution {
    public int findTarget(int[] arr, int target) {
        for(int i=0;i<arr.length;i++) if(arr[i]==target) return i;
        return -1;
    }
}
```

## Code (Python)

```python
class Solution:
    def findTarget(self, arr, target):
        for i in range(len(arr)):
            if arr[i] == target: return i
        return -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
