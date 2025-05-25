# *145. Pythagorean Triplet*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/pythagorean-triplet3018/1)

## **🧩 Problem Description**

Given an integer array `arr[]`, determine if there exists a triplet `(a, b, c)` in the array such that they satisfy the Pythagorean condition:


## Code(C++)
```cpp
class Solution {
  public:
    bool pythagoreanTriplet(vector<int>& arr) {
        unordered_set<int> s;
        for (int& x : arr) s.insert(x * x);
        for (int i = 0; i < arr.size(); ++i)
            for (int j = i + 1; j < arr.size(); ++j)
                if (s.count(arr[i]*arr[i] + arr[j]*arr[j])) return true;
        return false;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean pythagoreanTriplet(int[] arr) {
        HashSet<Integer> squares = new HashSet<>();
        for (int x : arr) squares.add(x * x);
        int n = arr.length;
        for (int i = 0; i < n; ++i)
            for (int j = i + 1; j < n; ++j)
                if (squares.contains(arr[i]*arr[i] + arr[j]*arr[j])) return true;
        return false;
    }
}
```

## Code (Python)

```python
class Solution:
    def pythagoreanTriplet(self, arr):
        s = set(x * x for x in arr)
        n = len(arr)
        for i in range(n):
            for j in range(i + 1, n):
                if arr[i]**2 + arr[j]**2 in s:
                    return True
        return False
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
