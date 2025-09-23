---
title: "🔄 Queue Reversal | GFG Solution 🚀"
keywords🏷️: ["🔄 queue reversal", "🔁 recursion", "📦 stack", "🗂️ data structures", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Queue Reversal problem: reverse all elements in a queue using recursion, stack, or auxiliary data structures. 🚀"
date: 📅 2025-09-23
---

# *266. Queue Reversal*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/queue-reversal/1)

## **🧩 Problem Description**

Given a queue `q` containing integer elements, your task is to **reverse the queue**. The queue should be modified in-place such that the first element becomes the last, the second element becomes the second last, and so on.

A queue follows the FIFO (First In First Out) principle, but after reversal, the elements should appear in LIFO (Last In First Out) order when dequeued.


## Code(C++)
```cpp
class Solution {
public:
    void reverseQueue(queue<int>& q) {
        if (q.empty()) return;
        int x = q.front();
        q.pop();
        reverseQueue(q);
        q.push(x);
    }
};
```

## Code (Java)

```java
class Solution {
    public void reverseQueue(Queue<Integer> q) {
        if (q.isEmpty()) return;
        int x = q.poll();
        reverseQueue(q);
        q.offer(x);
    }
}
```

## Code (Python)

```python
class Solution:
    def reverseQueue(self, q):
        s = []
        while q:
            s.append(q.popleft())
        while s:
            q.append(s.pop())
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
