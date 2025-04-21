--- ❤️ ---

# 🚀 _Day 111. First Repeating element_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/first-repeating-element/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <unordered_map>

using namespace std;

class Solution {
public:
    int solve(vector<int> &A) {
        unordered_map<int, int> elementCount;
        
        // Count occurrences of each element
        for (int num : A) {
            elementCount[num]++;
        }
        
        // Find the first element with count > 1
        for (int num : A) {
            if (elementCount[num] > 1) {
                return num;
            }
        }
        
        return -1;
    }
};
```

## Code (Java)

```java
import java.util.HashMap;

public class Solution {
    public int solve(int[] A) {
        HashMap<Integer, Integer> elementCount = new HashMap<>();
        
        // Count occurrences of each element
        for (int num : A) {
            elementCount.put(num, elementCount.getOrDefault(num, 0) + 1);
        }
        
        // Find the first element with count > 1
        for (int num : A) {
            if (elementCount.get(num) > 1) {
                return num;
            }
        }
        
        return -1;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return an integer
    def solve(self, A):
        # Create a dictionary to store the count of each element
        element_count = {}
        
        # Iterate through the array to populate the dictionary
        for num in A:
            if num in element_count:
                element_count[num] += 1
            else:
                element_count[num] = 1
        
        # Iterate through the array again to find the first element with count > 1
        for num in A:
            if element_count[num] > 1:
                return num
        
        # If no repeating element found, return -1
        return -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
