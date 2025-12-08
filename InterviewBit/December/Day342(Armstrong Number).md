--- ❤️ ---

# 🚀 _Day 342. Armstrong Number_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/armstrong-number/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int solve(int A) {
        string s = to_string(A);
        int n = s.length();
        long long sum = 0;

        for(char c : s) {
            int d = c - '0';
            long long p = 1;
            for(int i = 0; i < n; i++) p *= d;   // compute d^n
            sum += p;
        }

        return (sum == A) ? 1 : 0;
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
