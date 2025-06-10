--- ❤️ ---

# 🚀 _Day 161. Meeting rooms_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/meeting-rooms/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <queue>
#include <algorithm>
using namespace std;

class Solution {
public:
    int solve(vector<vector<int>>& A) {
        if (A.empty()) return 0;
        
        // Sort the meetings based on start time
        sort(A.begin(), A.end(), [](const vector<int>& a, const vector<int>& b) {
            return a[0] < b[0];
        });
        
        // Use a min-heap to keep track of end times
        priority_queue<int, vector<int>, greater<int>> min_heap;
        min_heap.push(A[0][1]);
        
        for (int i = 1; i < A.size(); ++i) {
            int start = A[i][0];
            int end = A[i][1];
            
            // If the current meeting starts after the earliest ending meeting, reuse that room
            if (start >= min_heap.top()) {
                min_heap.pop();
            }
            
            // Push the current meeting's end time into the heap
            min_heap.push(end);
        }
        
        // The size of the heap is the minimum number of rooms needed
        return min_heap.size();
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(ArrayList<ArrayList<Integer>> A) {
        if (A.isEmpty()) return 0;
        
        // Sort the meetings based on start time
        Collections.sort(A, new Comparator<ArrayList<Integer>>() {
            public int compare(ArrayList<Integer> a, ArrayList<Integer> b) {
                return a.get(0).compareTo(b.get(0));
            }
        });
        
        // Use a min-heap to keep track of end times
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.add(A.get(0).get(1));
        
        for (int i = 1; i < A.size(); ++i) {
            int start = A.get(i).get(0);
            int end = A.get(i).get(1);
            
            // If the current meeting starts after the earliest ending meeting, reuse that room
            if (start >= minHeap.peek()) {
                minHeap.poll();
            }
            
            // Push the current meeting's end time into the heap
            minHeap.add(end);
        }
        
        // The size of the heap is the minimum number of rooms needed
        return minHeap.size();
    }
}
```

## Code (Python)

```python
import heapq

class Solution:
    # @param A : list of list of integers
    # @return an integer
    def solve(self, A):
        if not A:
            return 0
        
        # Sort the meetings based on start time
        A.sort(key=lambda x: x[0])
        
        # Use a min-heap to keep track of end times
        heap = []
        heapq.heappush(heap, A[0][1])
        
        for meeting in A[1:]:
            start, end = meeting
            # If the current meeting starts after the earliest ending meeting, reuse that room
            if start >= heap[0]:
                heapq.heappop(heap)
            # Push the current meeting's end time into the heap
            heapq.heappush(heap, end)
        
        # The size of the heap is the minimum number of rooms needed
        return len(heap)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
