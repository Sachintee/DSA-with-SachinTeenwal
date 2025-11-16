--- ❤️ ---

# 🚀 _Day 319. Count the Number of Substrings With Dominant One_ 🧠


The problem can be found at the following link: [Problem Link]()

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
    def numberOfSubstrings(self, s: str) -> int:
        n = len(s)
        nxt = [n] * (n + 1)
        for i in range(n - 1, -1, -1):
            nxt[i] = nxt[i + 1]
            if s[i] == "0":
                nxt[i] = i
        ans = 0
        for i in range(n):
            cnt0 = int(s[i] == "0")
            j = i
            while j < n and cnt0 * cnt0 <= n:
                cnt1 = (nxt[j + 1] - i) - cnt0
                if cnt1 >= cnt0 * cnt0:
                    ans += min(nxt[j + 1] - j, cnt1 - cnt0 * cnt0 + 1)
                j = nxt[j + 1]
                cnt0 += 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
