--- ❤️ ---

# 🚀 _Day 245. Priority Queue_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/priority_queue/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

int solve(vector<int> &A) {
    // Min-heap
    priority_queue<int, vector<int>, greater<int>> pq(A.begin(), A.end());
    
    long long totalCost = 0;  // Use long long to avoid overflow for large inputs
    
    while (pq.size() > 1) {
        int first = pq.top(); pq.pop();
        int second = pq.top(); pq.pop();
        
        int cost = first + second;
        totalCost += cost;
        
        pq.push(cost);
    }
    
    return (int)totalCost;
}

```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int solve(int[] A) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();
        
        for (int num : A) {
            pq.offer(num);
        }
        
        long totalCost = 0;
        
        while (pq.size() > 1) {
            int first = pq.poll();
            int second = pq.poll();
            
            int cost = first + second;
            totalCost += cost;
            
            pq.offer(cost);
        }
        
        return (int) totalCost;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        int[] A = {1, 2, 3, 4, 5};
        System.out.println(sol.solve(A));  // Output: 33
    }
}

```

## Code (Python3)

```python
import heapq

def solve(A):
    # Convert list into a min-heap
    heapq.heapify(A)
    total_cost = 0

    while len(A) > 1:
        first = heapq.heappop(A)
        second = heapq.heappop(A)
        
        cost = first + second
        total_cost += cost
        
        heapq.heappush(A, cost)
    
    return total_cost


# Example usage
A = [1, 2, 3, 4, 5]
print(solve(A))  # Output: 33

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
