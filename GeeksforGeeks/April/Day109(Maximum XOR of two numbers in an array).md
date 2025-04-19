---
Difficulty: Medium
Source: 160 Days of Problem Solving
Tags:
  - Bit Magic
  - Tries
---

# 🚀 _Day 109. Maximum XOR of two numbers in an array_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tries-gfg-160/problem/maximum-xor-of-two-numbers-in-an-array)  

## 💡 **Problem Description:**

Given an array `arr[]` of **non-negative integers**, your task is to find the **maximum XOR** value that can be obtained by XORing any two distinct elements of the array.


## Code(C++)
```cpp
class Solution {
public:
    int maxXor(vector<int>& a) {
        int max_xor = 0, mask = 0;
        unordered_set<int> s;
        for(int i = 30; i >= 0; i--) {
            mask |= (1 << i);
            s.clear();
            int temp = max_xor | (1 << i);
            for(int num : a) {
                int prefix = num & mask;
                if(s.count(temp ^ prefix)) { max_xor = temp; break; }
                s.insert(prefix);
            }
        }
        return max_xor;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxXor(int[] arr) {
        int maxXor = 0, mask = 0;
        HashSet<Integer> set = new HashSet<>();
        for (int i = 30; i >= 0; i--) {
            mask |= (1 << i);
            set.clear();
            int temp = maxXor | (1 << i);
            boolean found = false;
            for (int num : arr) {
                int prefix = num & mask;
                if (set.contains(temp ^ prefix)) {
                    found = true;
                    break;
                }
                set.add(prefix);
            }
            if (found) maxXor = temp;
        }
        return maxXor;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxXor(self, arr):
        max_xor, mask = 0, 0
        for i in range(30, -1, -1):
            mask |= (1 << i)
            prefixes = set()
            temp = max_xor | (1 << i)
            found = False
            for num in arr:
                prefix = num & mask
                if (temp ^ prefix) in prefixes:
                    found = True
                    break
                prefixes.add(prefix)
            if found:
                max_xor = temp
        return max_xor
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
