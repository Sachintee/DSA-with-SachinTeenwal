# *115. Majority Element*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/majority-element-1587115620/1)


## **🧩 Problem Description**

Given an array `arr[]`, find the **majority element** in the array. A majority element is an element that appears **strictly more than** `arr.size() / 2` times.

If no such element exists, return `-1`.


## Code(C++)
```cpp
class Solution {
  public:
    int majorityElement(vector<int>& arr) {
        int count = 0, candidate;
        for (int num : arr) {
            if (count == 0) candidate = num;
            count += (num == candidate) ? 1 : -1;
        }
        count = 0;
        for (int num : arr) if (num == candidate) count++;
        return count > arr.size() / 2 ? candidate : -1;
    }
};
```

## Code (Java)

```java
class Solution {
    static int majorityElement(int[] a) {
        int cand=0, count=0;
        for (int v : a) {
            if (count == 0) cand = v;
            count += v == cand ? 1 : -1;
        }
        count = 0;
        for (int v : a) if (v == cand) count++;
        return count > a.length / 2 ? cand : -1;
    }
}
```

## Code (Python)

```python
class Solution:
    def majorityElement(self, a):
        count = cand = 0
        for v in a:
            if not count:
                cand = v
            count += 1 if v == cand else -1
        return cand if sum(1 for v in a if v == cand) > len(a)//2 else -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
