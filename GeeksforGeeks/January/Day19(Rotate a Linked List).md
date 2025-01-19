---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Linked-List
---

# 🚀 _Day 19.  Rotate a linked list_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/linked-list-gfg-160/problem/rotate-a-linked-list)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

class Node {
public:
    int data;
    Node* next;

    Node(int val) {
        data = val;
        next = nullptr;
    }
};

class Solution {
public:
    // Function to rotate a linked list.
    Node* rotate(Node* head, int k) {
        // If the linked list is empty or no rotations are needed,
        // return the original linked list
        if (k == 0 || head == nullptr)
            return head;

        Node* curr = head;
        int length = 1;

        // Find the length of the linked list
        while (curr->next != nullptr) {
            curr = curr->next;
            length++;
        }

        // Modulo k with the length of the linked list to handle
        // large values of k
        k %= length;

        if (k == 0)
            return head;

        // Make the linked list circular
        curr->next = head;

        // Traverse the linked list to find the kth node
        curr = head;
        for (int i = 1; i < k; i++) {
            curr = curr->next;
        }

        // Update the (k + 1)th node as the new head
        Node* newHead = curr->next;

        // Break the loop by updating the next pointer
        // of the kth node
        curr->next = nullptr;

        return newHead;
    }
};
```

## Code (Java)

```java
class Node {
    int data;
    Node next;

    // Constructor
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

class Solution {
    // Function to rotate a linked list.
    public Node rotate(Node head, int k) {
        // If the linked list is empty or no rotations are needed,
        // return the original linked list
        if (head == null || k == 0) {
            return head;
        }

        // Find the length of the linked list
        Node curr = head;
        int length = 1;
        while (curr.next != null) {
            curr = curr.next;
            length++;
        }

        // Modulo k with the length of the linked list to handle
        // large values of k
        k %= length;

        if (k == 0) {
            return head;
        }

        // Make the linked list circular
        curr.next = head;

        // Traverse the linked list to find the kth node
        curr = head;
        for (int i = 1; i < k; i++) {
            curr = curr.next;
        }

        // Update the (k + 1)th node as the new head
        Node newHead = curr.next;

        // Break the loop by updating the next pointer
        // of the kth node
        curr.next = null;

        return newHead;
    }
}
```

## Code (Python3)

```python
'''

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

'''


class Solution:

    #Function to rotate a linked list.
    def rotate(self, head, k):
        # If the linked list is empty or no rotations are needed,
        # return the original linked list
        if k == 0 or head is None:
            return head

        curr = head
        length = 1

        # Find the length of the linked list
        while curr.next is not None:
            curr = curr.next
            length += 1

        # Modulo k with length of linked list to handle
        # large values of k
        k %= length

        if k == 0:
            curr.next = None
            return head

        # Make the linked list circular
        curr.next = head

        # Traverse the linked list to find the kth node
        curr = head
        for _ in range(1, k):
            curr = curr.next

        # Update the (k + 1)th node as the new head
        newHead = curr.next

        # Break the loop by updating the next pointer
        # of kth node
        curr.next = None
        return newHead
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>984</h4>
