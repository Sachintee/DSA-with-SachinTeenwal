---
title: "🔢 Form the Largest Number | GFG Solution 🔍"
keywords🏷️: ["🔢 largest number", "🔍 custom comparator", "📍 sorting", "📈 string manipulation", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Form the Largest Number problem: arrange integers to form the largest possible number using custom comparator sorting technique. 🚀"
date: 📅 2025-08-16
---

# *228. Form the Largest Number*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/largest-number-formed-from-an-array1117/1)

## **🧩 Problem Description**

You are given an array `arr[]` of non-negative integers. Your task is to arrange them so that after concatenating all of them in order, it results in the **largest possible number**. Since the result may be very large, return it as a string.

The key insight is that we need to sort the numbers based on which arrangement produces a larger concatenated result, not by their numerical values.


## Code(C++)
```cpp
class Solution {
public:
    string findLargest(vector<int>& arr) {
        vector<string> s;
        for (int x : arr) s.push_back(to_string(x));
        sort(s.begin(), s.end(), [](const string& x, const string& y) { 
            return x + y > y + x; 
        });
        if (s[0] == "0") return "0";
        string result;
        for (const string& str : s) result += str;
        return result;
    }
};
```

## Code (Java)

```java
class Solution {
    public String findLargest(int[] arr) {
        String[] s = new String[arr.length];
        for (int i = 0; i < arr.length; i++) s[i] = String.valueOf(arr[i]);
        Arrays.sort(s, (x, y) -> (x + y).compareTo(y + x) > 0 ? -1 : 1); 
        if (s[0].equals("0")) return "0";
        StringBuilder res = new StringBuilder();
        Arrays.stream(s).forEach(res::append);
        return res.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def findLargest(self, arr):
        s = sorted(map(str, arr), key=cmp_to_key(lambda x, y: -1 if x + y > y + x else 1))
        return '0' if s[0] == '0' else ''.join(s)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
