---
Difficulty: Hard  
Source: 160 Days of Problem Solving  
Tags:
  - Heap
  - Design-Pattern
---

# 🚀 _Day 51. Find median in a stream_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/heap-gfg-160/problem/find-median-in-a-stream-1587115620)  

## 💡 **Problem Description:**

Given a **data stream** `arr[]`, where integers are read sequentially, determine the **median** of the elements encountered **so far** after each new integer is read.  


## Code(C++)
```cpp
class Solution {
public:
    vector<double> getMedian(vector<int>& arr) {
        priority_queue<int> maxHeap;
        priority_queue<int, vector<int>, greater<int>> minHeap;
        vector<double> res;

        for (int num : arr) {
            if (maxHeap.empty() || num <= maxHeap.top()) maxHeap.push(num);
            else minHeap.push(num);

            if (maxHeap.size() > minHeap.size() + 1) minHeap.push(maxHeap.top()), maxHeap.pop();
            else if (minHeap.size() > maxHeap.size()) maxHeap.push(minHeap.top()), minHeap.pop();

            res.push_back(maxHeap.size() > minHeap.size() ? maxHeap.top() : (maxHeap.top() + minHeap.top()) / 2.0);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Double> getMedian(int[] arr) {
        PriorityQueue<Integer> maxH = new PriorityQueue<>(Collections.reverseOrder());
        PriorityQueue<Integer> minH = new PriorityQueue<>();
        ArrayList<Double> res = new ArrayList<>();

        for (int n : arr) {
            maxH.add(n);
            minH.add(maxH.poll());
            if (maxH.size() < minH.size()) maxH.add(minH.poll());
            res.add(maxH.size() > minH.size() ? (double) maxH.peek() : (maxH.peek() + minH.peek()) / 2.0);
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def getMedian(self, arr):
        maxHeap, minHeap = [], []
        res = []

        for num in arr:
            heapq.heappush(maxHeap, -num)
            heapq.heappush(minHeap, -heapq.heappop(maxHeap))

            if len(maxHeap) < len(minHeap):
                heapq.heappush(maxHeap, -heapq.heappop(minHeap))

            res.append(float(-maxHeap[0]) if len(maxHeap) > len(minHeap) else (-maxHeap[0] + minHeap[0]) / 2.0)
        
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
