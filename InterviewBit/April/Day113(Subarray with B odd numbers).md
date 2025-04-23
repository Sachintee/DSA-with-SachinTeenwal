--- ❤️ ---

# 🚀 _Day 113. Subarray with B odd numbers_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/subarray-with-b-odd-numbers/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    int solve(vector<int> &A, int B) {
        unordered_map<int, int> count;
        count[0] = 1;  // base case
        int odd_count = 0, result = 0;

        for (int num : A) {
            if (num % 2 == 1)
                odd_count++;

            if (count.find(odd_count - B) != count.end()) {
                result += count[odd_count - B];
            }

            count[odd_count]++;
        }

        return result;
    }
};

```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(int[] A, int B) {
        Map<Integer, Integer> count = new HashMap<>();
        count.put(0, 1);  // base case

        int oddCount = 0, result = 0;

        for (int num : A) {
            if (num % 2 != 0)
                oddCount++;

            result += count.getOrDefault(oddCount - B, 0);
            count.put(oddCount, count.getOrDefault(oddCount, 0) + 1);
        }

        return result;
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @param B : integer
    # @return an integer
    def solve(self, A, B):
        from collections import defaultdict

        count = defaultdict(int)
        count[0] = 1  # base case: zero odd numbers before starting
        odd_count = 0
        result = 0

        for num in A:
            if num % 2 == 1:
                odd_count += 1

            # Check if (odd_count - B) has occurred before
            result += count[odd_count - B]

            # Increment frequency of current odd_count
            count[odd_count] += 1

        return result

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
