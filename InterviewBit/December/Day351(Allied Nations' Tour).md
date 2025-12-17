--- ❤️ ---

# 🚀 _Day 351. Allied Nations' Tour_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/allied-nations-tour/)

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
    def solve(self, A, B, C, D, E):
        MOD = 10**9 + 7

        # blocked[day] = set of cities attacked on that day
        blocked = [set() for _ in range(C + 1)]
        for day, city in D:
            blocked[day].add(city)

        # dp arrays
        prev = [0] * (A + 2)
        prev[B] = 1  # start at city B on day 0

        for day in range(1, C + 1):
            curr = [0] * (A + 2)

            # prefix sum of prev
            prefix = [0] * (A + 2)
            for i in range(1, A + 1):
                prefix[i] = (prefix[i - 1] + prev[i]) % MOD

            for city in range(1, A + 1):
                if city in blocked[day]:
                    continue

                left = max(1, city - E)
                right = min(A, city + E)

                curr[city] = (prefix[right] - prefix[left - 1]) % MOD

            prev = curr

        return sum(prev) % MOD

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

