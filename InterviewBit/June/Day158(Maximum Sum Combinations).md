--- ❤️ ---

# 🚀 _Day 158. Maximum Sum Combinations_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/maximum-sum-combinations/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <queue>
#include <algorithm>
#include <unordered_set>

using namespace std;

vector<int> solve(vector<int>& A, vector<int>& B, int C) {
    sort(A.rbegin(), A.rend());
    sort(B.rbegin(), B.rend());
    
    priority_queue<pair<int, pair<int, int>>> max_heap;
    unordered_set<string> visited;
    
    max_heap.push({A[0] + B[0], {0, 0}});
    visited.insert("0,0");
    
    vector<int> result;
    
    while (C-- && !max_heap.empty()) {
        auto current = max_heap.top();
        max_heap.pop();
        int sum = current.first;
        int i = current.second.first;
        int j = current.second.second;
        
        result.push_back(sum);
        
        if (i + 1 < A.size()) {
            string key = to_string(i + 1) + "," + to_string(j);
            if (visited.find(key) == visited.end()) {
                max_heap.push({A[i + 1] + B[j], {i + 1, j}});
                visited.insert(key);
            }
        }
        
        if (j + 1 < B.size()) {
            string key = to_string(i) + "," + to_string(j + 1);
            if (visited.find(key) == visited.end()) {
                max_heap.push({A[i] + B[j + 1], {i, j + 1}});
                visited.insert(key);
            }
        }
    }
    
    return result;
}
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public ArrayList<Integer> solve(ArrayList<Integer> A, ArrayList<Integer> B, int C) {
        Collections.sort(A, Collections.reverseOrder());
        Collections.sort(B, Collections.reverseOrder());
        
        PriorityQueue<int[]> maxHeap = new PriorityQueue<>((a, b) -> b[0] - a[0]);
        HashSet<String> visited = new HashSet<>();
        
        maxHeap.offer(new int[]{A.get(0) + B.get(0), 0, 0});
        visited.add("0,0");
        
        ArrayList<Integer> result = new ArrayList<>();
        
        while (C-- > 0 && !maxHeap.isEmpty()) {
            int[] current = maxHeap.poll();
            int sum = current[0];
            int i = current[1];
            int j = current[2];
            
            result.add(sum);
            
            if (i + 1 < A.size()) {
                String key = (i + 1) + "," + j;
                if (!visited.contains(key)) {
                    maxHeap.offer(new int[]{A.get(i + 1) + B.get(j), i + 1, j});
                    visited.add(key);
                }
            }
            
            if (j + 1 < B.size()) {
                String key = i + "," + (j + 1);
                if (!visited.contains(key)) {
                    maxHeap.offer(new int[]{A.get(i) + B.get(j + 1), i, j + 1});
                    visited.add(key);
                }
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
    # @param A : list of integers
    # @param B : list of integers
    # @param C : integer
    # @return a list of integers
    def solve(self, A, B, C):
        A.sort(reverse=True)
        B.sort(reverse=True)
        
        max_heap = []
        visited = set()
        
        heapq.heappush(max_heap, (-(A[0] + B[0]), 0, 0))
        visited.add((0, 0))
        
        result = []
        
        for _ in range(C):
            if not max_heap:
                break
            current = heapq.heappop(max_heap)
            current_sum = -current[0]
            i = current[1]
            j = current[2]
            
            result.append(current_sum)
            
            if i + 1 < len(A) and (i + 1, j) not in visited:
                heapq.heappush(max_heap, (-(A[i + 1] + B[j]), i + 1, j))
                visited.add((i + 1, j))
            
            if j + 1 < len(B) and (i, j + 1) not in visited:
                heapq.heappush(max_heap, (-(A[i] + B[j + 1]), i, j + 1))
                visited.add((i, j + 1))
        
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
