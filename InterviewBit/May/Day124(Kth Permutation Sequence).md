--- ❤️ ---

# 🚀 _Day 124. Kth Permutation Sequence_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/kth-permutation-sequence/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>
#include <algorithm>

using namespace std;

class Solution {
public:
    string getPermutation(int n, int k) {
        vector<int> numbers;
        for (int i = 1; i <= n; ++i) {
            numbers.push_back(i);
        }
        string result;
        k--; // convert to 0-based index
        int fact = 1;
        for (int i = 1; i <= n; ++i) {
            fact *= i;
        }
        for (int i = n; i >= 1; --i) {
            fact /= i;
            int index = k / fact;
            result += to_string(numbers[index]);
            numbers.erase(numbers.begin() + index);
            k %= fact;
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
    public String getPermutation(int n, int k) {
        List<Integer> numbers = new ArrayList<>();
        for (int i = 1; i <= n; ++i) {
            numbers.add(i);
        }
        StringBuilder result = new StringBuilder();
        k--; // convert to 0-based index
        int fact = 1;
        for (int i = 1; i <= n; ++i) {
            fact *= i;
        }
        for (int i = n; i >= 1; --i) {
            fact /= i;
            int index = k / fact;
            result.append(numbers.remove(index));
            k %= fact;
        }
        return result.toString();
    }
}
```

## Code (Python)

```python
import math

class Solution:
    # @param A : integer
    # @param B : integer
    # @return a strings
    def getPermutation(self, n, k):
        numbers = list(range(1, n + 1))
        k -= 1  # convert to 0-based index
        result = []
        
        for i in range(n, 0, -1):
            fact = math.factorial(i - 1)
            index = k // fact
            result.append(str(numbers.pop(index)))
            k %= fact
        
        return ''.join(result)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
