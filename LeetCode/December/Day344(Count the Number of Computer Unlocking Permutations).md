--- ❤️ ---

# 🚀 _Day 344. Count the Number of Computer Unlocking Permutations_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-the-number-of-computer-unlocking-permutations/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countPermutations(vector<int>& complexity) {
        const int mod = 1e9 + 7;
        long long ans = 1;
        for (int i = 1; i < complexity.size(); ++i) {
            if (complexity[i] <= complexity[0]) {
                return 0;
            }
            ans = ans * i % mod;
        }
        return ans;
    }
};
```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
