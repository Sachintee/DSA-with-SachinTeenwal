---
title: "🔗 Merge K Sorted Linked Lists | GFG Solution 🚀"
keywords🏷️: ["🔗 linked lists", "🏷️ merge", "📊 min heap", "📈 priority queue", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to merge K sorted linked lists: combine multiple sorted linked lists into one using min heap and divide & conquer approaches. 🚀"
date: 📅 2025-09-07
---

# *250. Merge K Sorted Linked Lists*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/merge-k-sorted-linked-lists/1)

## **🧩 Problem Description**

You are given an array `arr[]` of `n` sorted linked lists of different sizes. Your task is to **merge all these lists** into a **single sorted linked list** and return the head of the merged list.

Each linked list is already sorted in ascending order. The goal is to efficiently combine them while maintaining the sorted order of elements.


## Code(C++)
```cpp
class Solution {
public:
    Node* mergeKLists(vector<Node*>& arr) {
        auto cmp = [](Node* a, Node* b) { return a->data > b->data; };
        priority_queue<Node*, vector<Node*>, decltype(cmp)> pq(cmp);
        
        for (Node* head : arr) if (head) pq.push(head);
        
        Node dummy(-1), *tail = &dummy;
        while (!pq.empty()) {
            Node* node = pq.top(); pq.pop();
            tail->next = node; tail = node;
            if (node->next) pq.push(node->next);
        }
        return dummy.next;
    }
};
```

## Code (Java)

```java
class Solution {
    Node mergeKLists(Node[] arr) {
        PriorityQueue<Node> pq = new PriorityQueue<>((a, b) -> a.data - b.data);
        for (Node head : arr) if (head != null) pq.offer(head);
        
        Node dummy = new Node(-1), tail = dummy;
        while (!pq.isEmpty()) {
            Node node = pq.poll();
            tail.next = node; tail = node;
            if (node.next != null) pq.offer(node.next);
        }
        return dummy.next;
    }
}
```

## Code (Python3)

```python
import heapq

class Solution:
    def mergeKLists(self, arr):
        heap = []
        for i, head in enumerate(arr):
            if head: heapq.heappush(heap, (head.data, i, head))
        
        dummy = Node(-1)
        tail = dummy
        while heap:
            _, i, node = heapq.heappop(heap)
            tail.next = node
            tail = node
            if node.next: heapq.heappush(heap, (node.next.data, i, node.next))
        return dummy.next
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
