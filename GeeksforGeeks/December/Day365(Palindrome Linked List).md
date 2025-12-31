
# 🚀 _Day 365. Palindrome Linked List_ 


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/check-if-linked-list-is-pallindrome/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    bool isPalindrome(Node *head) {
        if (!head || !head->next) return true;

        // 1. Find middle (slow-fast pointers)
        Node *slow = head, *fast = head;
        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;
        }

        // 2. Reverse second half
        Node *prev = NULL, *curr = slow;
        while (curr) {
            Node *next = curr->next;
            curr->next = prev;
            prev = curr;
            curr = next;
        }

        // 3. Compare first half and reversed second half
        Node *first = head, *second = prev;
        while (second) {
            if (first->data != second->data)
                return false;
            first = first->next;
            second = second->next;
        }

        return true;
    }
};

```

## Code (Java)

```java
class Solution {
    public boolean isPalindrome(Node head) {
        if (head == null || head.next == null)
            return true;

        // 1. Find middle
        Node slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }

        // 2. Reverse second half
        Node prev = null, curr = slow;
        while (curr != null) {
            Node next = curr.next;
            curr.next = prev;
            prev = curr;
            curr = next;
        }

        // 3. Compare
        Node first = head, second = prev;
        while (second != null) {
            if (first.data != second.data)
                return false;
            first = first.next;
            second = second.next;
        }

        return true;
    }
}

```

## Code (Python3)

```python
class Solution:
    def isPalindrome(self, head):
        if not head or not head.next:
            return True

        # 1. Find middle
        slow = fast = head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next

        # 2. Reverse second half
        prev = None
        curr = slow
        while curr:
            nxt = curr.next
            curr.next = prev
            prev = curr
            curr = nxt

        # 3. Compare both halves
        first = head
        second = prev
        while second:
            if first.data != second.data:
                return False
            first = first.next
            second = second.next

        return True

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
