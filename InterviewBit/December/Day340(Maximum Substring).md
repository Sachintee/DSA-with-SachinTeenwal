--- ❤️ ---

# 🚀 _Day 340. Maximum Substring_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/maximum-substring/)

## 🎯 **My Approach:**


## Code(C++)
```cpp

```

## Code (Java)

```java

```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        n = len(A)
        ans = 0
        
        for i in range(0, n, B):
            substring = A[i : i + B]
            count_a = substring.count('a')
            ans = max(ans, count_a)
        
        return ans

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
