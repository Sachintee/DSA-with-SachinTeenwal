---
title: "🔗 Linked List Group Reverse | GFG Solution 🔄"
keywords🏷️: ["🔗 linked list", "🔄 group reversal", "📍 two pointers", "🔁 recursion", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Linked List Group Reverse problem: reverse every k nodes in a linked list including remaining nodes using recursive and iterative approaches. 🚀"
date: 📅 2025-09-04
---

# *247. Linked List Group Reverse*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/reverse-a-linked-list-in-groups-of-given-size/1)

## **🧩 Problem Description**

You are given the head of a **Singly linked list**. Your task is to **reverse every k nodes** in the linked list and return the head of the modified list.

**Note:** If the number of nodes is not a multiple of k, then the left-out nodes at the end should be considered as a group and **must be reversed**.

A group reversal means that within each group of k consecutive nodes, the order should be completely reversed while maintaining the overall structure of the linked list.


## Code(C++)
```cpp
class Solution {
public:
    Node* reverseKGroup(Node* head, int k) {
        Node* cur = head; int cnt = 0;
        while (cur && cnt < k) { cur = cur->next; cnt++; }
        if (cnt < k) {
            Node* prev = nullptr;
            while (head) {
                Node* nxt = head->next; head->next = prev; prev = head; head = nxt;
            }
            return prev;
        }
        cur = reverseKGroup(cur, k);
        while (cnt--) {
            Node* nxt = head->next; head->next = cur; cur = head; head = nxt;
        }
        return cur;
    }
};
```

## Code (Java)

```java
class Solution {
    public Node reverseKGroup(Node head, int k) {
        Node cur = head; int cnt = 0;
        while (cur != null && cnt < k) { cur = cur.next; cnt++; }
        if (cnt < k) {
            Node prev = null;
            while (head != null) {
                Node nxt = head.next; head.next = prev; prev = head; head = nxt;
            }
            return prev;
        }
        cur = reverseKGroup(cur, k);
        while (cnt-- > 0) {
            Node nxt = head.next; head.next = cur; cur = head; head = nxt;
        }
        return cur;
    }
}
```

## Code (Python)

```python
class Solution:
    def reverseKGroup(self, head, k):
        cur, cnt = head, 0
        while cur and cnt < k:
            cur = cur.next; cnt += 1
        if cnt < k:
            prev = None
            while head:
                nxt = head.next; head.next = prev; prev = head; head = nxt
            return prev
        cur = self.reverseKGroup(cur, k)
        while cnt:
            nxt = head.next; head.next = cur; cur = head; head = nxt; cnt -= 1
        return cur
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
