--- ❤️ ---

# 🚀 _Day 294. Top K Frequent in Array_ 🧠

Given a non-empty integer array arr[]. Your task is to find and return the top k elements which have the highest frequency in the array.
Note: If two numbers have the same frequency, the larger number should be given the higher priority.
The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/top-k-frequent-elements-in-array/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    vector<int> topKFreq(vector<int> &arr, int k) {
        unordered_map<int, int> freq;

        // Step 1: Count frequency
        for (int num : arr)
            freq[num]++;

        // Step 2: Create max heap (sort by freq, then by value)
        priority_queue<pair<int, int>> pq;
        for (auto &p : freq) {
            pq.push({p.second * 1000000 + p.first, p.first});
        }

        // Step 3: Extract top k
        vector<int> result;
        while (k-- && !pq.empty()) {
            result.push_back(pq.top().second);
            pq.pop();
        }

        return result;
    }
};

```

## Code (Java)

```java
import java.util.*;

class Solution {
    public List<Integer> topKFreq(int[] arr, int k) {
        Map<Integer, Integer> freq = new HashMap<>();
        for (int num : arr)
            freq.put(num, freq.getOrDefault(num, 0) + 1);

        // Custom comparator: higher freq first, then larger number first
        PriorityQueue<int[]> pq = new PriorityQueue<>(
            (a, b) -> (a[0] == b[0]) ? b[1] - a[1] : b[0] - a[0]
        );

        for (Map.Entry<Integer, Integer> entry : freq.entrySet()) {
            pq.add(new int[]{entry.getValue(), entry.getKey()});
        }

        List<Integer> result = new ArrayList<>();
        while (k-- > 0 && !pq.isEmpty()) {
            result.add(pq.poll()[1]);
        }

        return result;
    }
}

```

## Code (Python)

```python
from collections import Counter
import heapq

class Solution:
    def topKFreq(self, arr, k):
        freq = Counter(arr)
        
        # Use a max heap: (-freq, -num) to handle both conditions
        heap = [(-f, -n) for n, f in freq.items()]
        heapq.heapify(heap)
        
        result = []
        for _ in range(k):
            result.append(-heapq.heappop(heap)[1])
        return result

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
