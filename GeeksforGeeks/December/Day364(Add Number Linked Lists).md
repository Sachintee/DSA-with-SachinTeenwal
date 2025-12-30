

# 🚀 _Day 364. Add Number Linked Lists_ 


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/add-two-numbers-represented-by-linked-lists/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
private:
    Node* reverse(Node* head) {
        Node* prev = NULL;
        while (head) {
            Node* next = head->next;
            head->next = prev;
            prev = head;
            head = next;
        }
        return prev;
    }

    Node* removeLeadingZeros(Node* head) {
        while (head && head->data == 0)
            head = head->next;
        return head ? head : new Node(0);
    }

public:
    Node* addTwoLists(Node* head1, Node* head2) {

        // Step 1: Remove leading zeros
        head1 = removeLeadingZeros(head1);
        head2 = removeLeadingZeros(head2);

        // Step 2: Reverse both lists
        head1 = reverse(head1);
        head2 = reverse(head2);

        // Step 3: Add numbers
        Node* dummy = new Node(0);
        Node* curr = dummy;
        int carry = 0;

        while (head1 || head2 || carry) {
            int sum = carry;

            if (head1) {
                sum += head1->data;
                head1 = head1->next;
            }
            if (head2) {
                sum += head2->data;
                head2 = head2->next;
            }

            carry = sum / 10;
            curr->next = new Node(sum % 10);
            curr = curr->next;
        }

        // Step 4: Reverse result
        Node* result = reverse(dummy->next);

        // Step 5: Remove leading zeros (if any)
        return removeLeadingZeros(result);
    }
};

```

## Code (Java)

```java
class Solution {

    private Node reverse(Node head) {
        Node prev = null;
        while (head != null) {
            Node next = head.next;
            head.next = prev;
            prev = head;
            head = next;
        }
        return prev;
    }

    private Node removeZeros(Node head) {
        while (head != null && head.data == 0)
            head = head.next;
        return head != null ? head : new Node(0);
    }

    public Node addTwoLists(Node head1, Node head2) {

        head1 = removeZeros(head1);
        head2 = removeZeros(head2);

        head1 = reverse(head1);
        head2 = reverse(head2);

        int carry = 0;
        Node dummy = new Node(0);
        Node curr = dummy;

        while (head1 != null || head2 != null || carry != 0) {
            int sum = carry;

            if (head1 != null) {
                sum += head1.data;
                head1 = head1.next;
            }
            if (head2 != null) {
                sum += head2.data;
                head2 = head2.next;
            }

            carry = sum / 10;
            curr.next = new Node(sum % 10);
            curr = curr.next;
        }

        return removeZeros(reverse(dummy.next));
    }
}

```

## Code (Python3)

```python
class Solution:
    def addTwoLists(self, head1, head2):
        def reverse(head):
            prev = None
            while head:
                nxt = head.next
                head.next = prev
                prev = head
                head = nxt
            return prev

        def removeZeros(head):
            while head and head.data == 0:
                head = head.next
            return head if head else Node(0)

        head1 = removeZeros(head1)
        head2 = removeZeros(head2)

        head1 = reverse(head1)
        head2 = reverse(head2)

        carry = 0
        dummy = Node(0)
        curr = dummy

        while head1 or head2 or carry:
            s = carry
            if head1:
                s += head1.data
                head1 = head1.next
            if head2:
                s += head2.data
                head2 = head2.next

            carry = s // 10
            curr.next = Node(s % 10)
            curr = curr.next

        return removeZeros(reverse(dummy.next))

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
