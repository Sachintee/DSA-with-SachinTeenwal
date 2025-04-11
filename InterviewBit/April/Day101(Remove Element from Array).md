--- ❤️ ---

# 🚀 _Day 101. Remove Element from Array
_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/remove-element-from-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>

using namespace std;

class Solution {
public:
    int removeElement(vector<int>& A, int B) {
        int j = 0;
        for (int i = 0; i < A.size(); ++i) {
            if (A[i] != B) {
                A[j] = A[i];
                j++;
            }
        }
        return j;
    }
};
```

## Code (Java)

```java
import java.util.ArrayList;

public class Solution {
    public int removeElement(ArrayList<Integer> A, int B) {
        int j = 0;
        for (int i = 0; i < A.size(); i++) {
            if (A.get(i) != B) {
                A.set(j, A.get(i));
                j++;
            }
        }
        return j;
    }
}
```

## Code (Python)

```python
class Solution:
    def removeElement(self, A, B):
        j = 0
        for i in range(len(A)):
            if A[i] != B:
                A[j] = A[i]
                j += 1
        return j
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
