--- ❤️ ---

# 🚀 _Day 56. Occurence of Each Number_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/occurence-of-each-number/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <map>
#include <algorithm>

using namespace std;

vector<int> Solution::findOccurences(vector<int> &A) {
    // Count the occurrences of each number
    map<int, int> freq;
    for (int num : A) {
        freq[num]++;
    }
    
    // Create the result list of occurrences in the required order
    vector<int> result;
    for (auto &pair : freq) {
        result.push_back(pair.second);
    }
    
    return result;
}
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int[] findOccurences(int[] A) {
        // Count the occurrences of each number
        Map<Integer, Integer> freq = new HashMap<>();
        for (int num : A) {
            freq.put(num, freq.getOrDefault(num, 0) + 1);
        }
        
        // Sort the numbers in ascending order
        List<Integer> sortedNums = new ArrayList<>(freq.keySet());
        Collections.sort(sortedNums);
        
        // Create the result array of occurrences in the required order
        int[] result = new int[sortedNums.size()];
        for (int i = 0; i < sortedNums.size(); i++) {
            result[i] = freq.get(sortedNums.get(i));
        }
        
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    def findOccurences(self, A):
        # Count the occurrences of each number
        freq = {}
        for num in A:
            if num in freq:
                freq[num] += 1
            else:
                freq[num] = 1
        
        # Sort the numbers in ascending order
        sorted_nums = sorted(freq.keys())
        
        # Create the result list of occurrences in the required order
        result = [freq[num] for num in sorted_nums]
        
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
