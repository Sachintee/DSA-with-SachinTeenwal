---
title: "🔗 Merge Sort for Linked List | GFG Solution 🔀"
keywords🏷️: ["🔗 linked list sorting", "🔀 merge sort", "📍 divide and conquer", "📈 recursion", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Merge Sort for Linked List problem: efficiently sort a linked list using divide and conquer approach with merge sort algorithm. 🚀"
date: 📅 2025-09-08
---

# *251. Merge Sort for Linked List*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/sort-a-linked-list/1)

## **🧩 Problem Description**

You are given the head of a linked list. Your task is to sort the given linked list using **Merge Sort** algorithm.

Merge Sort is a divide-and-conquer algorithm that works by recursively dividing the list into smaller sublists, sorting them, and then merging them back together in sorted order.


## Code(C++)
```cpp
class Solution {
public:
    Node *mergeSort(Node *h) {
        if (!h || !h->next) return h;
        Node *s = h, *f = h->next;
        while (f && f->next) s = s->next, f = f->next->next;
        Node *r = s->next;
        s->next = nullptr;
        return merge(mergeSort(h), mergeSort(r));
    }
    
    Node *merge(Node *a, Node *b) {
        if (!a) return b;
        if (!b) return a;
        if (a->data <= b->data) {
            a->next = merge(a->next, b);
            return a;
        }
        b->next = merge(a, b->next);
        return b;
    }
};
```

## Code (Java)

```java
class Solution {
    public Node mergeSort(Node h) {
        if (h == null || h.next == null) return h;
        Node s = h, f = h.next;
        while (f != null && f.next != null) {
            s = s.next;
            f = f.next.next;
        }
        Node r = s.next;
        s.next = null;
        return merge(mergeSort(h), mergeSort(r));
    }
    
    Node merge(Node a, Node b) {
        if (a == null) return b;
        if (b == null) return a;
        if (a.data <= b.data) {
            a.next = merge(a.next, b);
            return a;
        }
        b.next = merge(a, b.next);
        return b;
    }
}
```

## Code (Python)

```python
class Solution:
    def mergeSort(self, h):
        if not h or not h.next: return h
        s, f = h, h.next
        while f and f.next:
            s, f = s.next, f.next.next
        r = s.next
        s.next = None
        return self.merge(self.mergeSort(h), self.mergeSort(r))
    
    def merge(self, a, b):
        if not a: return b
        if not b: return a
        if a.data <= b.data:
            a.next = self.merge(a.next, b)
            return a
        b.next = self.merge(a, b.next)
        return b
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
