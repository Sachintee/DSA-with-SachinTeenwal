# *146. Insert in Sorted Circular Linked List*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/sorted-insert-for-circular-linked-list/1)


## **🧩 Problem Description**

Given a sorted circular linked list, insert a new node containing a given `data` value into the list so that it remains a sorted circular linked list.



## Code(C++)
```cpp
class Solution {
  public:
    Node* sortedInsert(Node* head, int data) {
        Node* n = new Node(data);
        if (!head) {
            n->next = n;
            return n;
        }
        Node* cur = head;
        while (true) {
            Node* nxt = cur->next;
            if ((cur->data <= data && data <= nxt->data) ||
                (cur->data > nxt->data && (data >= cur->data || data <= nxt->data)) ||
                nxt == head) {
                cur->next = n;
                n->next = nxt;
                if (data < head->data) head = n;
                break;
            }
            cur = nxt;
        }
        return head;
    }
};
```

## Code (Java)

```java
class Solution {
    public Node sortedInsert(Node head, int data) {
        Node n = new Node(data);
        if (head == null) {
            n.next = n;
            return n;
        }
        Node cur = head;
        while (true) {
            if ((cur.data <= data && cur.next.data >= data) ||
                (cur.data > cur.next.data && (data >= cur.data || data <= cur.next.data)) ||
                cur.next == head) {
                n.next = cur.next;
                cur.next = n;
                if (data < head.data) head = n;
                break;
            }
            cur = cur.next;
        }
        return head;
    }
}
```

## Code (Python)

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
     

class Solution:
    def sortedInsert(self, head, data):
        n = Node(data)
        if not head:
            n.next = n
            return n
        cur = head
        while True:
            if (cur.data <= data <= cur.next.data or
                cur.data > cur.next.data and (data >= cur.data or data <= cur.next.data) or
                cur.next == head):
                n.next = cur.next
                cur.next = n
                if data < head.data:
                    head = n
                break
            cur = cur.next
        return head
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
