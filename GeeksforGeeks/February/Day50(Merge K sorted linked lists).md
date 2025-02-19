---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Heap
  - Linked List
---

# 🚀 _Day 50. Merge K sorted linked lists_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/heap-gfg-160/problem/merge-k-sorted-linked-lists)  


## 💡 **Problem Description:**

Given an array **arr[]** of **n sorted linked lists** of different sizes, merge them into a **single sorted linked list** and return the head of the merged list.  

## Code(C++)
```cpp
class Solution {
public:
    Node* mergeKLists(vector<Node*>& l) {
        auto c=[](Node* a,Node* b){return a->data>b->data;};
        priority_queue<Node*,vector<Node*>,decltype(c)> pq(c);
        for(auto x:l) if(x) pq.push(x);
        Node d(0),*t=&d;
        while(!pq.empty()){
            t->next=pq.top(); t=pq.top(); pq.pop();
            if(t->next) pq.push(t->next);
        }
        return d.next;
    }
};
```

## Code (Java)

```java
class Solution {
    public Node mergeKLists(List<Node> lists) {
        PriorityQueue<Node> pq = new PriorityQueue<>(Comparator.comparingInt(a -> a.data));
        for (Node head : lists) if (head != null) pq.add(head);
        Node dummy = new Node(0), tail = dummy;
        while (!pq.isEmpty()) {
            tail.next = pq.poll();
            tail = tail.next;
            if (tail.next != null) pq.add(tail.next);
        }
        return dummy.next;
    }
}
```

## Code (Python)

```python
class Solution:
    def mergeKLists(self, lists):
        heap = [(node.data, i, node) for i, node in enumerate(lists) if node]
        heapq.heapify(heap)
        dummy = tail = Node(0)
        while heap:
            _, i, node = heapq.heappop(heap)
            tail.next, tail = node, node
            if node.next:
                heapq.heappush(heap, (node.next.data, i, node.next))
        return dummy.next
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
