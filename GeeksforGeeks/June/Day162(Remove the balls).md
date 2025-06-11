---
title: "🎯 Remove the Balls | GFG Solution 🔵🔴"
keywords🏷️: ["🟣 remove balls", "🧹 stack removal", "🧠 in-place optimization", "📘 GFG", "💥 duplicate removal", "🔁 repeated pair", "🧮 DSA", "🏁 competitive programming"]
description: "✅ GFG solution to the 'Remove the Balls' problem: simulate consecutive removal of matching balls using stack or in-place logic. 🚀"
date: 📅 2025-06-11
---

# *162. Remove the Balls*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/remove-the-balls--170647/1)


## **🧩 Problem Description**

You are given two arrays `color[]` and `radius[]`, representing a sequence of balls:

* `color[i]` denotes the color of the i-th ball.
* `radius[i]` denotes the radius of the i-th ball.

👉 If **two consecutive balls** have the **same color** and **same radius**, they are removed.
🧹 This removal process is repeated until no more such adjacent pairs exist.

🧮 Your task is to return the **number of balls remaining** after all possible removals.


## Code(C++)
```cpp
class Solution {
public:
    int findLength(vector<int>& color, vector<int>& radius) {
        int n = color.size(), j = -1;
        for (int i = 0; i < n; ++i) {
            if (j >= 0 && color[i] == color[j] && radius[i] == radius[j])
                --j;
            else {
                ++j;
                color[j] = color[i];
                radius[j] = radius[i];
            }
        }
        return j + 1;
    }
};
```

## Code (Java)

```java
class Solution {
    public int findLength(int[] color, int[] radius) {
        int j = -1;
        for (int i = 0; i < color.length; ++i) {
            if (j >= 0 && color[i] == color[j] && radius[i] == radius[j])
                j--;
            else {
                ++j;
                color[j] = color[i];
                radius[j] = radius[i];
            }
        }
        return j + 1;
    }
}
```

## Code (Python)

```python
class Solution:
    def findLength(self, color, radius):
        j = -1
        for i, (c, r) in enumerate(zip(color, radius)):
            if j >= 0 and c == color[j] and r == radius[j]:
                j -= 1
            else:
                j += 1
                color[j], radius[j] = c, r
        return j + 1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
