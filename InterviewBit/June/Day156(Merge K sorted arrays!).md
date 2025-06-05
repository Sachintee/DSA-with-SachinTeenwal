--- ❤️ ---

# 🚀 _Day 156. Merge K sorted arrays!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/merge-k-sorted-arrays/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <queue>
using namespace std;

class Solution {
public:
    vector<int> solve(vector<vector<int>>& A) {
        vector<int> result;
        if (A.empty()) return result;
        
        // Min-heap: stores tuples of (value, array index, element index)
        priority_queue<pair<int, pair<int, int>>, vector<pair<int, pair<int, int>>>, greater<pair<int, pair<int, int>>>> min_heap;
        
        // Initialize the heap with the first element of each array
        for (int i = 0; i < A.size(); ++i) {
            if (!A[i].empty()) {
                min_heap.push({A[i][0], {i, 0}});
            }
        }
        
        while (!min_heap.empty()) {
            auto current = min_heap.top();
            min_heap.pop();
            int val = current.first;
            int arr_idx = current.second.first;
            int elem_idx = current.second.second;
            
            result.push_back(val);
            
            // Move to the next element in the same array if it exists
            if (elem_idx + 1 < A[arr_idx].size()) {
                min_heap.push({A[arr_idx][elem_idx + 1], {arr_idx, elem_idx + 1}});
            }
        }
        
        return result;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public ArrayList<Integer> solve(ArrayList<ArrayList<Integer>> A) {
        ArrayList<Integer> result = new ArrayList<>();
        if (A == null || A.size() == 0) return result;
        
        // Min-heap: stores arrays of [value, array index, element index]
        PriorityQueue<int[]> minHeap = new PriorityQueue<>((a, b) -> a[0] - b[0]);
        
        // Initialize the heap with the first element of each array
        for (int i = 0; i < A.size(); i++) {
            if (A.get(i).size() > 0) {
                minHeap.offer(new int[]{A.get(i).get(0), i, 0});
            }
        }
        
        while (!minHeap.isEmpty()) {
            int[] current = minHeap.poll();
            int val = current[0];
            int arrIdx = current[1];
            int elemIdx = current[2];
            
            result.add(val);
            
            // Move to the next element in the same array if it exists
            if (elemIdx + 1 < A.get(arrIdx).size()) {
                minHeap.offer(new int[]{A.get(arrIdx).get(elemIdx + 1), arrIdx, elemIdx + 1});
            }
        }
        
        return result;
    }
}
```

## Code (Python)

```python
import heapq

class Solution:
    # @param A : list of list of integers
    # @return a list of integers
    def solve(self, A):
        min_heap = []
        result = []
        
        # Initialize the heap with the first element of each array, along with the array index and element index
        for i in range(len(A)):
            if A[i]:  # Check if the array is not empty
                heapq.heappush(min_heap, (A[i][0], i, 0))
        
        while min_heap:
            val, arr_idx, elem_idx = heapq.heappop(min_heap)
            result.append(val)
            
            # Move to the next element in the same array if it exists
            if elem_idx + 1 < len(A[arr_idx]):
                next_elem = A[arr_idx][elem_idx + 1]
                heapq.heappush(min_heap, (next_elem, arr_idx, elem_idx + 1))
        
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
