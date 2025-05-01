--- ❤️ ---

# 🚀 _Day 121. Gray Code_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/gray-code/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <cmath>

using namespace std;

class Solution {
public:
    vector<int> grayCode(int n) {
        vector<int> result;
        if (n == 0) {
            result.push_back(0);
            return result;
        }
        vector<int> prev = grayCode(n - 1);
        result = prev;
        int mask = 1 << (n - 1);
        for (int i = prev.size() - 1; i >= 0; --i) {
            result.push_back(mask + prev[i]);
        }
        return result;
    }
};
```

## Code (Java)

```java
import java.util.ArrayList;
import java.util.List;

class Solution {
    public List<Integer> grayCode(int n) {
        List<Integer> result = new ArrayList<>();
        if (n == 0) {
            result.add(0);
            return result;
        }
        List<Integer> prev = grayCode(n - 1);
        result.addAll(prev);
        int mask = 1 << (n - 1);
        for (int i = prev.size() - 1; i >= 0; --i) {
            result.add(mask + prev.get(i));
        }
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : integer
    # @return a list of integers
    def grayCode(self, A):
        if A == 0:
            return [0]
        # Generate the sequence for A-1
        prev_gray = self.grayCode(A - 1)
        # The sequence for A is the previous sequence followed by the reverse of the previous sequence with 1 << (A-1) added
        result = prev_gray.copy()
        mask = 1 << (A - 1)
        for code in reversed(prev_gray):
            result.append(mask + code)
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
