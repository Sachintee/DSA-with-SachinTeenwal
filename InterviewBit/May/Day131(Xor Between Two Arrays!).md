--- ❤️ ---

# 🚀 _Day 131. Xor Between Two Arrays!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/xor-between-two-arrays/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    int solve(vector<int>& A, vector<int>& B) {
        int max_xor = 0;
        for (int a : A) {
            for (int b : B) {
                int current_xor = a ^ b;
                if (current_xor > max_xor) {
                    max_xor = current_xor;
                }
            }
        }
        return max_xor;
    }
};
```

## Code (Java)

```java
import java.util.List;

public class Solution {
    public int solve(List<Integer> A, List<Integer> B) {
        int maxXor = 0;
        for (int a : A) {
            for (int b : B) {
                int currentXor = a ^ b;
                if (currentXor > maxXor) {
                    maxXor = currentXor;
                }
            }
        }
        return maxXor;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @param B : list of integers
    # @return an integer
    def solve(self, A, B):
        max_xor = 0
        # Build a trie for all numbers in B
        trie = {}
        for num in B:
            node = trie
            for i in range(31, -1, -1):
                bit = (num >> i) & 1
                if bit not in node:
                    node[bit] = {}
                node = node[bit]
        # For each number in A, find the number in B that maximizes XOR
        for num in A:
            current_xor = 0
            node = trie
            for i in range(31, -1, -1):
                bit = (num >> i) & 1
                toggled_bit = 1 - bit
                if toggled_bit in node:
                    current_xor += (1 << i)
                    node = node[toggled_bit]
                else:
                    node = node[bit]
            if current_xor > max_xor:
                max_xor = current_xor
        return max_xor
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
