# *119. Sort a Linked List of 0s, 1s, and 2s*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/given-a-linked-list-of-0s-1s-and-2s-sort-it/1)

## **🧩 Problem Description**

Given the head of a linked list where each node contains a value of either `0`, `1`, or `2`, your task is to rearrange the list such that all `0`s appear first, followed by all `1`s, and all `2`s appear at the end.

## Code(C++)
```cpp
class Solution {
  public:
    Node* segregate(Node* head) {
        int count[3] = {0};
        for (Node* curr = head; curr; curr = curr->next) count[curr->data]++;
        Node* curr = head;
        for (int i = 0; i < 3; i++)
            while (count[i]--) curr->data = i, curr = curr->next;
        return head;
    }
};
```

## Code (Java)

```java
class Solution {
    static Node segregate(Node head) {
        int[] count = new int[3];
        for (Node curr = head; curr != null; curr = curr.next) count[curr.data]++;
        Node curr = head;
        for (int i = 0; i < 3; i++)
            while (count[i]-- > 0) { curr.data = i; curr = curr.next; }
        return head;
    }
}
```

## Code (Python)

```python
class Solution:
    def segregate(self, head):
        count = [0, 0, 0]
        curr = head
        while curr:
            count[curr.data] += 1
            curr = curr.next
        curr = head
        for i in range(3):
            while count[i]:
                curr.data = i
                curr = curr.next
                count[i] -= 1
        return head
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
