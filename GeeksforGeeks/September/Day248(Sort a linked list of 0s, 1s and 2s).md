---
title: "🔗 Sort a Linked List of 0s, 1s and 2s | GFG Solution 🎯"
keywords🏷️: ["🔗 linked list sorting", "🎯 three-way partitioning", "📍 pointer manipulation", "🚀 node segregation", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Sort a Linked List of 0s, 1s and 2s problem: segregate nodes containing 0s, 1s, and 2s using optimal pointer manipulation technique. 🚀"
date: 📅 2025-09-05
---

# *248. Sort a Linked List of 0s, 1s and 2s*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/given-a-linked-list-of-0s-1s-and-2s-sort-it/1)

## **🧩 Problem Description**

Given the head of a linked list where nodes can contain values **0s, 1s, and 2s only**. Your task is to rearrange the list so that all **0s appear at the beginning**, followed by all **1s**, and all **2s are placed at the end**.

A linked list is a linear data structure where elements are stored in nodes, and each node contains data and a reference to the next node. The goal is to segregate the nodes based on their data values while maintaining the relative order within each group.


## Code(C++)
```cpp
class Solution {
public:
    Node* segregate(Node* head) {
        if (!head) return head;
        Node* zero = nullptr, *one = nullptr, *two = nullptr;
        Node* zeroTail = nullptr, *oneTail = nullptr, *twoTail = nullptr;
        
        while (head) {
            Node* next = head->next;
            head->next = nullptr;
            
            if (head->data == 0) {
                if (!zero) zero = zeroTail = head;
                else zeroTail = zeroTail->next = head;
            } else if (head->data == 1) {
                if (!one) one = oneTail = head;
                else oneTail = oneTail->next = head;
            } else {
                if (!two) two = twoTail = head;
                else twoTail = twoTail->next = head;
            }
            head = next;
        }
        
        if (zeroTail) {
            head = zero;
            zeroTail->next = one ? one : two;
            if (oneTail) oneTail->next = two;
        } else if (oneTail) {
            head = one;
            oneTail->next = two;
        } else {
            head = two;
        }
        
        return head;
    }
};
```

## Code (Java)

```java
class Solution {
    public Node segregate(Node head) {
        if (head == null) return head;
        
        Node zero = null, one = null, two = null;
        Node zTail = null, oTail = null, tTail = null;
        
        while (head != null) {
            Node next = head.next;
            head.next = null;
            
            if (head.data == 0) {
                if (zero == null) zero = zTail = head;
                else zTail = zTail.next = head;
            } else if (head.data == 1) {
                if (one == null) one = oTail = head;
                else oTail = oTail.next = head;
            } else {
                if (two == null) two = tTail = head;
                else tTail = tTail.next = head;
            }
            head = next;
        }
        
        if (zTail != null) {
            head = zero;
            zTail.next = (one != null) ? one : two;
            if (oTail != null) oTail.next = two;
        } else if (oTail != null) {
            head = one;
            oTail.next = two;
        } else {
            head = two;
        }
        
        return head;
    }
}
```

## Code (Python)

```python
class Solution:
    def segregate(self, head):
        if not head:
            return head
            
        zero = one = two = None
        z_tail = o_tail = t_tail = None
        
        while head:
            next_node = head.next
            head.next = None
            
            if head.data == 0:
                if not zero:
                    zero = z_tail = head
                else:
                    z_tail.next = head
                    z_tail = head
            elif head.data == 1:
                if not one:
                    one = o_tail = head
                else:
                    o_tail.next = head
                    o_tail = head
            else:
                if not two:
                    two = t_tail = head
                else:
                    t_tail.next = head
                    t_tail = head
            head = next_node
        
        if z_tail:
            head = zero
            z_tail.next = one if one else two
            if o_tail:
                o_tail.next = two
        elif o_tail:
            head = one
            o_tail.next = two
        else:
            head = two
            
        return head
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
