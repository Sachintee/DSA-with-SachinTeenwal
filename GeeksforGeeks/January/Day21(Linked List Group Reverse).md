---
Difficulty: Hard 
Source: 160 Days of Problem Solving  
Tags:
  - Linked-List
---

# 🚀 _Day 21. Linked List Group Reverse_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/linked-list-gfg-160/problem/reverse-a-linked-list-in-groups-of-given-size)

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
    Node* reverseKGroup(Node* head, int k) {
        if (!head || k <= 1) return head;

        Node* curr = head;
        Node* newHead = nullptr;
        Node* tail = nullptr;

        while (curr) {
            Node* groupPrev = nullptr;
            Node* groupCurr = curr;
            int count = 0;

            while (curr && count < k) {
                Node* nextNode = curr->next;
                curr->next = groupPrev;
                groupPrev = curr;
                curr = nextNode;
                count++;
            }

            if (!newHead) {
                newHead = groupPrev;
            }

            if (tail) {
                tail->next = groupPrev;
            }

            tail = groupCurr;
        }

        return newHead;
    }
};

// Example usage
void printList(Node* head) {
    while (head) {
        cout << head->data << " ";
        head = head->next;
    }
    cout << endl;
}

int main() {
    Node* head = new Node(1);
    head->next = new Node(2);
    head->next->next = new Node(3);
    head->next->next->next = new Node(4);
    head->next->next->next->next = new Node(5);

    Solution sol;
    int k = 3;
    Node* newHead = sol.reverseKGroup(head, k);

    printList(newHead); // Output: 3 2 1 4 5

    return 0;
}
```

## Code (Java)

```java
class Node {
    int data;
    Node next;

    Node(int val) {
        data = val;
        next = null;
    }
}

class Solution {
    public Node reverseKGroup(Node head, int k) {
        if (head == null || k <= 1) return head;

        Node curr = head;
        Node newHead = null;
        Node tail = null;

        while (curr != null) {
            Node groupPrev = null;
            Node groupCurr = curr;
            int count = 0;

            while (curr != null && count < k) {
                Node nextNode = curr.next;
                curr.next = groupPrev;
                groupPrev = curr;
                curr = nextNode;
                count++;
            }

            if (newHead == null) {
                newHead = groupPrev;
            }

            if (tail != null) {
                tail.next = groupPrev;
            }

            tail = groupCurr;
        }

        return newHead;
    }

    // Helper to print linked list
    public static void printList(Node head) {
        while (head != null) {
            System.out.print(head.data + " ");
            head = head.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);
        head.next.next.next = new Node(4);
        head.next.next.next.next = new Node(5);

        Solution sol = new Solution();
        int k = 3;
        Node newHead = sol.reverseKGroup(head, k);

        printList(newHead); // Output: 3 2 1 4 5
    }
}
```

## Code (Python)

```python
"""Node is defined as

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
"""
"""Node is defined as

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
"""
class Solution:
    def reverseKGroup(self, head, k):
        # Code here
        if not head or k<=1:
            return head
        curr=head
        new_head=None
        tail=None
        while curr:
            group_prev=None
            group_curr=curr
            c=0
            while curr and c < k:
                next_node=curr.next
                curr.next=group_prev
                group_prev=curr
                curr=next_node
                c+=1
            if not new_head:
                new_head=group_prev
            if tail:
                tail.next=group_prev
            tail=group_curr
        return new_head

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>753</h4>
