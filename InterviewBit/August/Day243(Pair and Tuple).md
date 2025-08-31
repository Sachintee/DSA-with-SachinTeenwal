--- ❤️ ---

# 🚀 _Day 243. Pair and Tuple_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/pair-and-tuple/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maxWater(vector<int>& h) {
        int l = 0, r = h.size() - 1, ans = 0;
        while (l < r) {
            ans = max(ans, min(h[l], h[r]) * (r - l));
            h[l] < h[r] ? ++l : --r;
        }
        return ans;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {

    public static AbstractMap.SimpleEntry<Integer, Integer> findMaxMin(List<Integer> A) {
        int mx = Integer.MIN_VALUE;
        int mn = Integer.MAX_VALUE;
        for (int x : A) {
            mx = Math.max(mx, x);
            mn = Math.min(mn, x);
        }
        // returning pair as SimpleEntry
        return new AbstractMap.SimpleEntry<>(mx, mn);
    }

    public static int[] compute(List<Integer> A) {
        int total = 0, evenSum = 0, oddSum = 0;
        for (int x : A) {
            total += x;
            if (x % 2 == 0)
                evenSum += x;
            else
                oddSum += x;
        }
        return new int[]{total, evenSum, oddSum};
    }
}

```

## Code (Python3)

```python
from typing import List, Tuple

def findMaxMin(A: List[int]) -> Tuple[int, int]:
    # First value = max, second value = min
    return (max(A), min(A))

def compute(A: List[int]) -> Tuple[int, int, int]:
    total = sum(A)
    evenSum = sum(x for x in A if x % 2 == 0)
    oddSum = total - evenSum
    return (total, evenSum, oddSum)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
