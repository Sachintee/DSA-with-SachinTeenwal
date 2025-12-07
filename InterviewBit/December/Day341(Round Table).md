--- ❤️ ---

# 🚀 _Day 341. Round Table_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/round-table/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int solve(int A) {
        const long long MOD = 1000000007;
        long long fact = 1;

        // Compute A! % MOD
        for (int i = 1; i <= A; i++) {
            fact = (fact * i) % MOD;
        }

        // Multiply by 2 for the Ram–Shyam ordering
        return (2LL * fact) % MOD;
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
