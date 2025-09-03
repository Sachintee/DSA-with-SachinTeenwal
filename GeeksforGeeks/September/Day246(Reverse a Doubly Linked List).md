---
title: "🔗 Reverse a Doubly Linked List | GFG Solution 🔄"
keywords🏷️: ["🔗 doubly linked list", "🔄 reverse", "📍 two pointers", "📚 linked list", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Reverse a Doubly Linked List problem: efficiently reverse a doubly linked list by swapping next and prev pointers. 🚀"
date: 📅 2025-09-03
---

# *246. Reverse a Doubly Linked List*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/reverse-a-doubly-linked-list/1)

## **🧩 Problem Description**

You are given the head of a doubly linked list. Your task is to **reverse** the doubly linked list and return its head.

A doubly linked list is a data structure where each node contains data and two pointers: one pointing to the next node and another pointing to the previous node. To reverse it, we need to swap these pointer directions for every node.


## Code(C++)
```cpp
class Solution {
public:
    Node *reverse(Node *head) {
        if (!head || !head->next) return head;
        Node *curr = head, *temp;
        while (curr) {
            temp = curr->next;
            curr->next = curr->prev;
            curr->prev = temp;
            if (!temp) return curr;
            curr = temp;
        }
        return head;
    }
};
```

## Code (Java)

```java
class Solution {
    public Node reverse(Node head) {
        if (head == null || head.next == null) return head;
        Node curr = head, temp;
        while (curr != null) {
            temp = curr.next;
            curr.next = curr.prev;
            curr.prev = temp;
            if (temp == null) return curr;
            curr = temp;
        }
        return head;
    }
}
```

## Code (Python)

```python
class Solution:
    def reverse(self, head):
        if not head or not head.next: 
            return head
        curr = head
        while curr:
            curr.next, curr.prev = curr.prev, curr.next
            if not curr.prev: 
                return curr
            curr = curr.prev
        return head
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
