--- ❤️ ---

# 🚀 _Day 110. Pairs With Given Xor_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/pairs-with-given-xor/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <unordered_set>
using namespace std;

class Solution {
public:
    int solve(vector<int>& A, int B) {
        unordered_set<int> seen;
        int count = 0;
        for (int num : A) {
            int complement = num ^ B;
            if (seen.find(complement) != seen.end()) {
                count++;
            }
            seen.insert(num);
        }
        return count;
    }
};
```

## Code (Java)

```java
import java.util.HashSet;
import java.util.Set;

public class Solution {
    public int solve(int[] A, int B) {
        Set<Integer> seen = new HashSet<>();
        int count = 0;
        for (int num : A) {
            int complement = num ^ B;
            if (seen.contains(complement)) {
                count++;
            }
            seen.add(num);
        }
        return count;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        seen = set()
        count = 0
        for num in A:
            complement = num ^ B
            if complement in seen:
                count += 1
            seen.add(num)
        return count
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
