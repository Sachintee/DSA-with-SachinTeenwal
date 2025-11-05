--- ❤️ ---

# 🚀 _Day 309. Subarray with equal occurences!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/subarray-with-equal-occurences/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <unordered_map>
using namespace std;

class Solution {
public:
    int solve(vector<int>& A, int B, int C) {
        unordered_map<int, int> countMap;
        countMap[0] = 1;  // balance before starting
        
        int balance = 0;
        int total = 0;
        
        for (int num : A) {
            if (num == B) {
                balance++;
            } else if (num == C) {
                balance--;
            }
            // else balance remains unchanged
            
            total += countMap[balance];
            countMap[balance]++;
        }
        
        return total;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int solve(ArrayList<Integer> A, int B, int C) {
        HashMap<Integer, Integer> countMap = new HashMap<>();
        countMap.put(0, 1);  // balance before starting
        
        int balance = 0;
        int total = 0;
        
        for (int num : A) {
            if (num == B) {
                balance++;
            } else if (num == C) {
                balance--;
            }
            // else balance remains unchanged
            
            total += countMap.getOrDefault(balance, 0);
            countMap.put(balance, countMap.getOrDefault(balance, 0) + 1);
        }
        
        return total;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B, C):
        from collections import defaultdict
        
        count_map = defaultdict(int)
        count_map[0] = 1  # balance before starting
        
        balance = 0
        total = 0
        
        for num in A:
            if num == B:
                balance += 1
            elif num == C:
                balance -= 1
            # else balance unchanged
            
            total += count_map[balance]
            count_map[balance] += 1
        
        return total
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
