--- ❤️ ---

# 🚀 _Day 152. Sliding Window Maximum_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/sliding-window-maximum/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <deque>

using namespace std;

vector<int> slidingMaximum(const vector<int> &A, int B) {
    if (A.empty()) return {};
    if (B >= A.size()) {
        int max_val = *max_element(A.begin(), A.end());
        return {max_val};
    }
    
    deque<int> q;
    vector<int> result;
    
    for (int i = 0; i < A.size(); ++i) {
        // Remove elements not in the current window
        while (!q.empty() && q.front() <= i - B) {
            q.pop_front();
        }
        
        // Remove elements smaller than the current element from the end
        while (!q.empty() && A[q.back()] <= A[i]) {
            q.pop_back();
        }
        
        q.push_back(i);
        
        // Start adding to result once the window size is reached
        if (i >= B - 1) {
            result.push_back(A[q.front()]);
        }
    }
    
    return result;
}
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public ArrayList<Integer> slidingMaximum(final List<Integer> A, int B) {
        ArrayList<Integer> result = new ArrayList<>();
        if (A.isEmpty()) return result;
        if (B >= A.size()) {
            result.add(Collections.max(A));
            return result;
        }
        
        Deque<Integer> q = new ArrayDeque<>();
        
        for (int i = 0; i < A.size(); ++i) {
            // Remove elements not in the current window
            while (!q.isEmpty() && q.peekFirst() <= i - B) {
                q.pollFirst();
            }
            
            // Remove elements smaller than the current element from the end
            while (!q.isEmpty() && A.get(q.peekLast()) <= A.get(i)) {
                q.pollLast();
            }
            
            q.offerLast(i);
            
            // Start adding to result once the window size is reached
            if (i >= B - 1) {
                result.add(A.get(q.peekFirst()));
            }
        }
        
        return result;
    }
}
```

## Code (Python)

```python
from collections import deque

class Solution:
    # @param A : tuple of integers
    # @param B : integer
    # @return a list of integers
    def slidingMaximum(self, A, B):
        if not A:
            return []
        if B >= len(A):
            return [max(A)]
        
        q = deque()
        result = []
        
        for i in range(len(A)):
            # Remove elements not in the current window
            while q and q[0] <= i - B:
                q.popleft()
            
            # Remove elements smaller than the current element from the end
            while q and A[q[-1]] <= A[i]:
                q.pop()
            
            q.append(i)
            
            # Start adding to result once the window size is reached
            if i >= B - 1:
                result.append(A[q[0]])
        
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
