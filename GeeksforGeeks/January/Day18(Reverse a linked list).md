---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Linked-List
---

# 🚀 _Day 18. Reverse a linked list_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/linked-list-gfg-160/problem/reverse-a-linked-list)

## 🎯 **My Approach:**


## Solution
```cpp
// Node class
class Node {
public:
    int data;
    Node* next;

    // Constructor
    Node(int val) {
        data = val;
        next = nullptr;
    }
};

class Solution {
public:
    Node* reverseList(Node* head) {
        Node* prev = nullptr;
        Node* current = head;

        while (current != nullptr) {
            // Save the next node
            Node* nextNode = current->next;
            // Reverse the link
            current->next = prev;
            // Move the pointers forward
            prev = current;
            current = nextNode;
        }

        // Return the new head (previously the last node)
        return prev;
    }
};
```

## Code (Java)

```java
// Node class
class Node {
    int data;
    Node next;

    Node(int val) {
        data = val;
        next = null;
    }
}

class Solution {
    public Node reverseList(Node head) {
        Node prev = null;
        Node current = head;

        while (current != null) {
            // Save the next node
            Node nextNode = current.next;
            // Reverse the link
            current.next = prev;
            // Move the pointers forward
            prev = current;
            current = nextNode;
        }

        // Return the new head (previously the last node)
        return prev;
    }
}
```

## Code (Python)

```python
"""
# Node Class

class Node:
    def __init__(self, val):
        self.data = val
        self.next = None

"""

class Solution:
    def reverseList(self, head):
        prev = None
        current = head

        while current:
            next_node = current.next
            current.next = prev
            prev = current
            current = next_node

        return prev
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>485</h4>
