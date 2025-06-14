--- ❤️ ---

# 🚀 _Day 165. Gas Station_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/gas-station/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    int canCompleteCircuit(vector<int>& A, vector<int>& B) {
        int total_gas = 0, total_cost = 0;
        int current_gas = 0, start_index = 0;
        
        for (int i = 0; i < A.size(); ++i) {
            total_gas += A[i];
            total_cost += B[i];
            current_gas += A[i] - B[i];
            if (current_gas < 0) {
                start_index = i + 1;
                current_gas = 0;
            }
        }
        
        return (total_gas >= total_cost) ? (start_index < A.size() ? start_index : -1) : -1;
    }
};
```

## Code (Java)

```java
public class Solution {
    public int canCompleteCircuit(int[] A, int[] B) {
        int totalGas = 0, totalCost = 0;
        int currentGas = 0, startIndex = 0;
        
        for (int i = 0; i < A.length; i++) {
            totalGas += A[i];
            totalCost += B[i];
            currentGas += A[i] - B[i];
            if (currentGas < 0) {
                startIndex = i + 1;
                currentGas = 0;
            }
        }
        
        return (totalGas >= totalCost) ? (startIndex < A.length ? startIndex : -1) : -1;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : tuple of integers
    # @param B : tuple of integers
    # @return an integer
    def canCompleteCircuit(self, A, B):
        total_gas = 0
        total_cost = 0
        current_gas = 0
        start_index = 0
        
        for i in range(len(A)):
            total_gas += A[i]
            total_cost += B[i]
            current_gas += A[i] - B[i]
            if current_gas < 0:
                start_index = i + 1
                current_gas = 0
        
        if total_gas >= total_cost:
            return start_index if start_index < len(A) else -1
        else:
            return -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
