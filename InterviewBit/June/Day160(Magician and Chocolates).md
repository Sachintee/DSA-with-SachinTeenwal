--- ❤️ ---

# 🚀 _Day 160. Magician and Chocolates_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/magician-and-chocolates/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <queue>
#include <algorithm>
using namespace std;

class Solution {
public:
    int nchoc(int A, vector<int> &B) {
        priority_queue<int> max_heap;
        for (int num : B) {
            max_heap.push(num);
        }
        
        long long total = 0;
        const int mod = 1e9 + 7;
        
        for (int i = 0; i < A; ++i) {
            if (max_heap.empty()) break;
            int current = max_heap.top();
            max_heap.pop();
            total += current;
            total %= mod;
            int new_val = current / 2;
            if (new_val > 0) {
                max_heap.push(new_val);
            }
        }
        
        return total % mod;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int nchoc(int A, ArrayList<Integer> B) {
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
        for (int num : B) {
            maxHeap.add(num);
        }
        
        long total = 0;
        final int mod = (int)1e9 + 7;
        
        for (int i = 0; i < A; ++i) {
            if (maxHeap.isEmpty()) break;
            int current = maxHeap.poll();
            total += current;
            total %= mod;
            int newVal = current / 2;
            if (newVal > 0) {
                maxHeap.add(newVal);
            }
        }
        
        return (int)(total % mod);
    }
}
```

## Code (Python)

```python
import heapq

class Solution:
    def nchoc(self, A, B):
        max_heap = []
        for num in B:
            heapq.heappush(max_heap, -num)  # Using min-heap as max-heap by pushing negative values
        
        total = 0
        mod = 10**9 + 7
        
        for _ in range(A):
            if not max_heap:
                break
            current = -heapq.heappop(max_heap)
            total += current
            total %= mod
            new_val = current // 2
            if new_val > 0:
                heapq.heappush(max_heap, -new_val)
        
        return total % mod
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
