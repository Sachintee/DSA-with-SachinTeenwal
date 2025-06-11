--- ❤️ ---

# 🚀 _Day 162. Majority Element_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/majority-element/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int candidate = 0;
        int count = 0;
        for (int num : nums) {
            if (count == 0) {
                candidate = num;
                count = 1;
            } else if (num == candidate) {
                count++;
            } else {
                count--;
            }
        }
        return candidate;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int majorityElement(int[] nums) {
        int candidate = 0;
        int count = 0;
        for (int num : nums) {
            if (count == 0) {
                candidate = num;
                count = 1;
            } else if (num == candidate) {
                count++;
            } else {
                count--;
            }
        }
        return candidate;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : tuple of integers
    # @return an integer
    def majorityElement(self, A):
        candidate = None
        count = 0
        for num in A:
            if count == 0:
                candidate = num
                count = 1
            elif num == candidate:
                count += 1
            else:
                count -= 1
        return candidate
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
