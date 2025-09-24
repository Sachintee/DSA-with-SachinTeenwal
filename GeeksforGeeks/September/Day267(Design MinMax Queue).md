---
title: "🔢 Design MinMax Queue | GFG Solution 🔍"
keywords🏷️: ["🔢 min max queue", "🔍 deque", "📍 monotonic queue", "📈 data structure", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Design MinMax Queue problem: implement a queue with O(1) min/max operations using monotonic deques. 🚀"
date: 📅 2025-09-24
---

# *267. Design MinMax Queue*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/design-minmax-queue/1)

## **🧩 Problem Description**

Design a **SpecialQueue** data structure that functions like a normal queue but with additional support for retrieving the minimum and maximum element efficiently.

The SpecialQueue must support the following operations:
- **enqueue(x)**: Insert an element x at the rear of the queue.
- **dequeue()**: Remove the element from the front of the queue.
- **getFront()**: Return the front element without removing.
- **getMin()**: Return the minimum element in the queue in **O(1) time**.
- **getMax()**: Return the maximum element in the queue in **O(1) time**.

The queries are represented in numeric form:
- `1 x`: Call enqueue(x)
- `2`: Call dequeue()
- `3`: Call getFront()
- `4`: Call getMin()
- `5`: Call getMax()


## Code(C++)
```cpp
class SpecialQueue {
    queue<int> q;
    deque<int> mn, mx;
public:
    void enqueue(int x) {
        q.push(x);
        while (!mn.empty() && mn.back() > x) mn.pop_back();
        mn.push_back(x);
        while (!mx.empty() && mx.back() < x) mx.pop_back();
        mx.push_back(x);
    }
    void dequeue() {
        int f = q.front(); q.pop();
        if (f == mn.front()) mn.pop_front();
        if (f == mx.front()) mx.pop_front();
    }
    int getFront() { return q.front(); }
    int getMin() { return mn.front(); }
    int getMax() { return mx.front(); }
};
```

## Code (Java)

```java
class SpecialQueue {
    Queue<Integer> q = new LinkedList<>();
    Deque<Integer> mn = new ArrayDeque<>(), mx = new ArrayDeque<>();
    
    public void enqueue(int x) {
        q.offer(x);
        while (!mn.isEmpty() && mn.peekLast() > x) mn.pollLast();
        mn.offerLast(x);
        while (!mx.isEmpty() && mx.peekLast() < x) mx.pollLast();
        mx.offerLast(x);
    }
    
    public void dequeue() {
        int f = q.poll();
        if (f == mn.peekFirst()) mn.pollFirst();
        if (f == mx.peekFirst()) mx.pollFirst();
    }
    
    public int getFront() { return q.peek(); }
    public int getMin() { return mn.peekFirst(); }
    public int getMax() { return mx.peekFirst(); }
}
```

## Code (Python)

```python
from collections import deque

class SpecialQueue:
    def __init__(self):
        self.q = deque()
        self.mn = deque()
        self.mx = deque()
    
    def enqueue(self, x):
        self.q.append(x)
        while self.mn and self.mn[-1] > x: self.mn.pop()
        self.mn.append(x)
        while self.mx and self.mx[-1] < x: self.mx.pop()
        self.mx.append(x)
    
    def dequeue(self):
        f = self.q.popleft()
        if f == self.mn[0]: self.mn.popleft()
        if f == self.mx[0]: self.mx.popleft()
    
    def getFront(self): return self.q[0]
    def getMin(self): return self.mn[0]
    def getMax(self): return self.mx[0]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
