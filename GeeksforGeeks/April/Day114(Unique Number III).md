# *24. Unique Number III*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/find-element-occuring-once-when-all-other-are-present-thrice/1)


## **🧩 Problem Description**

Given an array `arr[]` where every element occurs **thrice** except one element which occurs **only once**, your task is to find that unique element.


## Code(C++)
```cpp
class Solution {
  public:
    int getSingle(vector<int> &arr) {
        int ones = 0, twos = 0;
        for (int num : arr) {
            ones = (ones ^ num) & ~twos;
            twos = (twos ^ num) & ~ones;
        }
        return ones;
    }
};
```

## Code (Java)

```java
class Solution {
    public int getSingle(int[] arr) {
        int ones = 0, twos = 0;
        for (int num : arr) {
            ones = (ones ^ num) & ~twos;
            twos = (twos ^ num) & ~ones;
        }
        return ones;
    }
}
```

## Code (Python)

```python
class Solution:
    def getSingle(self, arr):
        ones = twos = 0
        for num in arr:
            ones = (ones ^ num) & ~twos
            twos = (twos ^ num) & ~ones
        return ones
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
