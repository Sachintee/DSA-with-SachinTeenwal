--- ❤️ ---

# 🚀 _Day 102. Remove Duplicates from Sorted Array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/remove-duplicates-from-sorted-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>

using namespace std;

class Solution {
public:
    int removeDuplicates(vector<int>& A) {
        if (A.empty()) return 0;
        int j = 1;
        for (int i = 1; i < A.size(); ++i) {
            if (A[i] != A[i - 1]) {
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
    public int removeDuplicates(ArrayList<Integer> A) {
        if (A.isEmpty()) return 0;
        int j = 1;
        for (int i = 1; i < A.size(); i++) {
            if (!A.get(i).equals(A.get(i - 1))) {
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
    def removeDuplicates(self, A):
        if not A:
            return 0
        j = 1
        for i in range(1, len(A)):
            if A[i] != A[i-1]:
                A[j] = A[i]
                j += 1
        return j
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
