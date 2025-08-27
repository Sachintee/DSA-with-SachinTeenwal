---
title: "🔺 Count the Number of Possible Triangles | GFG Solution 📐"
keywords🏷️: ["🔺 triangle counting", "🔍 two pointers", "📊 sorting", "📈 geometric properties", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to count possible triangles problem: find number of valid triangles using triangle inequality theorem with efficient two-pointer technique. 🚀"
date: 📅 2025-08-27
---

# *239. Count the Number of Possible Triangles*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/count-possible-triangles-1587115620/1)

## **🧩 Problem Description**

Given an integer array `arr[]`, find the number of triangles that can be formed with three different array elements as lengths of three sides of the triangle. A triangle with three given sides is only possible if the sum of any two sides is always greater than the third side (Triangle Inequality Theorem).

For three sides `a`, `b`, and `c` to form a valid triangle:

## Code(C++)
```cpp
class Solution {
public:
    int countTriangles(vector<int>& a) {
        sort(a.begin(), a.end());
        int c = 0, n = a.size();
        for (int k = n - 1; k >= 2; --k) {
            int i = 0, j = k - 1;
            while (i < j) {
                if (a[i] + a[j] > a[k]) {
                    c += j - i;
                    --j;
                } else ++i;
            }
        }
        return c;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countTriangles(int[] a) {
        Arrays.sort(a);
        int c = 0, n = a.length;
        for (int k = n - 1; k >= 2; --k) {
            int i = 0, j = k - 1;
            while (i < j) {
                if (a[i] + a[j] > a[k]) {
                    c += j - i;
                    --j;
                } else ++i;
            }
        }
        return c;
    }
}
```

## Code (Python)

```python
class Solution:
    def countTriangles(self, a):
        a.sort()
        c, n = 0, len(a)
        for k in range(n - 1, 1, -1):
            i, j = 0, k - 1
            while i < j:
                if a[i] + a[j] > a[k]:
                    c += j - i
                    j -= 1
                else:
                    i += 1
        return c
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
