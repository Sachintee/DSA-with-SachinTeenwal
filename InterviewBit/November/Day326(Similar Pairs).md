--- ❤️ ---

# 🚀 _Day 326. Similar Pairs_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/similar-pairs/)

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
        MOD = 10**9 + 7
        n = len(A)
        
        freq = {}
        ans = 0
        i = 0
        
        for j in range(n):
            # Remove elements that are outside window (j - i > B)
            while j - i > B:
                freq[A[i]] -= 1
                if freq[A[i]] == 0:
                    del freq[A[i]]
                i += 1
            
            # Count existing equal values in window
            if A[j] in freq:
                ans = (ans + freq[A[j]]) % MOD
            
            # Add A[j] to frequency map
            freq[A[j]] = freq.get(A[j], 0) + 1
        
        return ans % MOD

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
