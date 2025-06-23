---
title: "💰 Minimum Sum | GFG Solution 🔍"
keywords🏷️: ["💰 minimum sum",  "➕ string addition", "🧮 greedy algorithm","🔢 digit manipulation", "📈 counting sort", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Minimum Sum problem: form two numbers using all digits to minimize their sum using greedy approach and counting sort. 🚀"
date: 📅 2025-06-23
---

# *174. Minimum Sum*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/minimum-sum4058/1)

## **🧩 Problem Description**

Given an array `arr[]` consisting of digits, your task is to form **two numbers** using all the digits such that their **sum is minimized**. Return the minimum possible sum as a string with **no leading zeroes**.

The key insight is to distribute the smallest digits optimally between two numbers to minimize their sum.


## Code(C++)
```cpp
class Solution {
public:
    string addString(string &s1, string &s2) {
        int i = s1.length() - 1, j = s2.length() - 1, carry = 0;
        string res = "";
        while (i >= 0 || j >= 0 || carry > 0) {
            int sum = carry;
            if (i >= 0) sum += (s1[i--] - '0');
            if (j >= 0) sum += (s2[j--] - '0');
            res.push_back(sum % 10 + '0');
            carry = sum / 10;
        }
        while (!res.empty() && res.back() == '0') res.pop_back();
        reverse(res.begin(), res.end());
        return res;
    }
    string minSum(vector<int> &arr) {
        vector<int> count(10, 0);
        for (int num : arr) count[num]++;
        string s1 = "", s2 = "";
        bool firstNum = true;
        for (int digit = 0; digit < 10; digit++) {
            while (count[digit]--) {
                if (firstNum) {
                    if (!(s1.empty() && digit == 0)) s1.push_back(digit + '0');
                    firstNum = false;
                } else {
                    if (!(s2.empty() && digit == 0)) s2.push_back(digit + '0');
                    firstNum = true;
                }
            }
        }
        if (s1.empty()) s1 = "0";
        if (s2.empty()) s2 = "0";
        return addString(s1, s2);
    }
};
```

## Code (Java)

```java
class Solution {
    String minSum(int[] arr) {
        int[] count = new int[10];
        for (int num : arr) count[num]++;
        StringBuilder s1 = new StringBuilder(), s2 = new StringBuilder();
        boolean firstNum = true;
        for (int d = 0; d < 10; d++) {
            while (count[d]-- > 0) {
                if (firstNum) {
                    if (!(s1.length() == 0 && d == 0)) s1.append(d);
                    firstNum = false;
                } else {
                    if (!(s2.length() == 0 && d == 0)) s2.append(d);
                    firstNum = true;
                }
            }
        }
        if (s1.length() == 0) s1.append('0');
        if (s2.length() == 0) s2.append('0');
        return addString(s1.toString(), s2.toString());
    }
    String addString(String s1, String s2) {
        int i = s1.length() - 1, j = s2.length() - 1, carry = 0;
        StringBuilder res = new StringBuilder();
        while (i >= 0 || j >= 0 || carry > 0) {
            int sum = carry;
            if (i >= 0) sum += s1.charAt(i--) - '0';
            if (j >= 0) sum += s2.charAt(j--) - '0';
            res.append(sum % 10);
            carry = sum / 10;
        }
        while (res.length() > 1 && res.charAt(res.length() - 1) == '0')
            res.deleteCharAt(res.length() - 1);
        return res.reverse().toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def minSum(self, arr):
        count = [0]*10
        for x in arr: count[x]+=1
        s1 = s2 = ""
        first = True
        for d in range(10):
            while count[d]>0:
                if first:
                    if s1 or d!=0: s1 += str(d)
                    first = False
                else:
                    if s2 or d!=0: s2 += str(d)
                    first = True
                count[d] -= 1
        if not s1: s1="0"
        if not s2: s2="0"
        return self.addString(s1, s2)
    def addString(self, s1, s2):
        i, j, carry, res = len(s1)-1, len(s2)-1, 0, []
        while i>=0 or j>=0 or carry>0:
            if i>=0: carry += int(s1[i]); i-=1
            if j>=0: carry += int(s2[j]); j-=1
            res.append(str(carry%10))
            carry//=10
        while len(res)>1 and res[-1]=='0': res.pop()
        return ''.join(reversed(res))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
