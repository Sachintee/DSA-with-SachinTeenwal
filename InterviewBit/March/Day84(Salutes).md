--- ❤️ ---

# 🚀 _Day 84. Salutes_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/salutes/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <string>
using namespace std;

class Solution {
public:
    long countSalutes(string A) {
        long total_salutes = 0;
        long count_right = 0;
        for (char c : A) {
            if (c == '>') {
                count_right++;
            } else {
                total_salutes += count_right;
            }
        }
        return total_salutes;
    }
};
```

## Code (Java)

```java
public class Solution {
    public long countSalutes(String A) {
        long totalSalutes = 0;
        long countRight = 0;
        for (int i = 0; i < A.length(); i++) {
            char c = A.charAt(i);
            if (c == '>') {
                countRight++;
            } else {
                totalSalutes += countRight;
            }
        }
        return totalSalutes;
    }
}
```

## Code (Python)

```python
class Solution:
    def countSalutes(self, A):
        total_salutes = 0
        count_right = 0
        for char in A:
            if char == '>':
                count_right += 1
            else:
                total_salutes += count_right
        return total_salutes
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
