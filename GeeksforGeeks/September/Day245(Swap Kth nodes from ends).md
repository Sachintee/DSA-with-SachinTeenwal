---
title: "🔗 Swap Kth Nodes from Ends | GFG Solution 🔄"
keywords🏷️: ["🔗 linked list", "🔄 node swapping", "📍 two pointers", "🎯 kth element", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to swap kth nodes from beginning and end of a singly linked list: efficient pointer manipulation technique with optimal time complexity. 🚀"
date: 📅 2025-09-02
---

# *245. Swap Kth Nodes from Ends*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/swap-kth-node-from-beginning-and-kth-node-from-end-in-a-singly-linked-list/1)

## **🧩 Problem Description**

Given the head of a singly linked list and an integer `k`, swap the kth node (1-based index) from the beginning and the kth node from the end of the linked list. Return the head of the final formed list and if it's not possible to swap the nodes return the original list.

The task involves identifying two specific nodes based on their positions from opposite ends and performing a complete node swap while maintaining the integrity of the linked list structure.

## Code(C++)
```cpp
class Solution {
public:
    Node* swapKth(Node* head, int k) {
        if (!head) return head;
        int n = 0;
        for (Node* t = head; t; t = t->next) n++;
        if (k > n || 2 * k - 1 == n) return head;
        
        Node *x = head, *y = head, *px = nullptr, *py = nullptr;
        for (int i = 1; i < k; i++) px = x, x = x->next;
        for (int i = 1; i < n - k + 1; i++) py = y, y = y->next;
        
        if (px) px->next = y; else head = y;
        if (py) py->next = x; else head = x;
        
        Node* temp = x->next;
        x->next = y->next;
        y->next = temp;
        
        return head;
    }
};
```

## Code (Java)

```java
class Solution {
    public Node swapKth(Node head, int k) {
        if (head == null) return head;
        int n = 0;
        for (Node t = head; t != null; t = t.next) n++;
        if (k > n || 2 * k - 1 == n) return head;
        
        Node x = head, y = head, px = null, py = null;
        for (int i = 1; i < k; i++) { px = x; x = x.next; }
        for (int i = 1; i < n - k + 1; i++) { py = y; y = y.next; }
        
        if (px != null) px.next = y; else head = y;
        if (py != null) py.next = x; else head = x;
        
        Node temp = x.next;
        x.next = y.next;
        y.next = temp;
        
        return head;
    }
}
```

## Code (Python3)

```python
class Solution:
    def swapKth(self, head, k):
        if not head: return head
        n, t = 0, head
        while t: n, t = n + 1, t.next
        if k > n or 2 * k - 1 == n: return head
        
        x, y, px, py = head, head, None, None
        for _ in range(k - 1): px, x = x, x.next
        for _ in range(n - k): py, y = y, y.next
        
        if px: px.next = y
        else: head = y
        if py: py.next = x  
        else: head = x
        
        x.next, y.next = y.next, x.next
        return head
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
