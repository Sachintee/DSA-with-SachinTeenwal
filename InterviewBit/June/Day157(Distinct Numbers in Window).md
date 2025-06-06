--- ❤️ ---

# 🚀 _Day 157. Distinct Numbers in Window_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/distinct-numbers-in-window/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <unordered_map>
using namespace std;

class Solution {
public:
    vector<int> dNums(vector<int>& A, int B) {
        vector<int> result;
        if (B > A.size()) {
            return result;
        }
        
        unordered_map<int, int> freq;
        
        // Initialize the frequency map for the first window
        for (int i = 0; i < B; ++i) {
            freq[A[i]]++;
        }
        result.push_back(freq.size());
        
        // Slide the window through the array
        for (int i = B; i < A.size(); ++i) {
            // Remove the element going out of the window (leftmost element of previous window)
            int left_element = A[i - B];
            if (freq[left_element] == 1) {
                freq.erase(left_element);
            } else {
                freq[left_element]--;
            }
            
            // Add the new element entering the window (rightmost element of current window)
            int new_element = A[i];
            freq[new_element]++;
            
            // Append the count of distinct elements in the current window
            result.push_back(freq.size());
        }
        
        return result;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public ArrayList<Integer> dNums(ArrayList<Integer> A, int B) {
        ArrayList<Integer> result = new ArrayList<>();
        if (B > A.size()) {
            return result;
        }
        
        HashMap<Integer, Integer> freq = new HashMap<>();
        
        // Initialize the frequency map for the first window
        for (int i = 0; i < B; i++) {
            int num = A.get(i);
            freq.put(num, freq.getOrDefault(num, 0) + 1);
        }
        result.add(freq.size());
        
        // Slide the window through the array
        for (int i = B; i < A.size(); i++) {
            // Remove the element going out of the window (leftmost element of previous window)
            int leftElement = A.get(i - B);
            if (freq.get(leftElement) == 1) {
                freq.remove(leftElement);
            } else {
                freq.put(leftElement, freq.get(leftElement) - 1);
            }
            
            // Add the new element entering the window (rightmost element of current window)
            int newElement = A.get(i);
            freq.put(newElement, freq.getOrDefault(newElement, 0) + 1);
            
            // Append the count of distinct elements in the current window
            result.add(freq.size());
        }
        
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @param B : integer
    # @return a list of integers
    def dNums(self, A, B):
        if B > len(A):
            return []
        
        freq = {}
        result = []
        
        # Initialize the frequency map for the first window
        for i in range(B):
            freq[A[i]] = freq.get(A[i], 0) + 1
        result.append(len(freq))
        
        # Slide the window through the array
        for i in range(B, len(A)):
            # Remove the element going out of the window (leftmost element of previous window)
            left_element = A[i - B]
            if freq[left_element] == 1:
                del freq[left_element]
            else:
                freq[left_element] -= 1
            
            # Add the new element entering the window (rightmost element of current window)
            new_element = A[i]
            freq[new_element] = freq.get(new_element, 0) + 1
            
            # Append the count of distinct elements in the current window
            result.append(len(freq))
        
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
