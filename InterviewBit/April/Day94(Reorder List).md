--- ❤️ ---

# 🚀 _Day 94. Reorder List_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/reorder-list/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    void reorderList(ListNode* head) {
        if (!head || !head->next) return;
        
        // Step 1: Find the middle of the list
        ListNode *slow = head, *fast = head;
        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;
        }
        
        // Step 2: Split the list into two halves
        ListNode *second_half = slow->next;
        slow->next = nullptr;
        
        // Step 3: Reverse the second half
        ListNode *prev = nullptr, *current = second_half, *next_node = nullptr;
        while (current) {
            next_node = current->next;
            current->next = prev;
            prev = current;
            current = next_node;
        }
        second_half = prev;
        
        // Step 4: Merge the two halves alternately
        ListNode *first_half = head;
        while (second_half) {
            ListNode *temp1 = first_half->next;
            ListNode *temp2 = second_half->next;
            first_half->next = second_half;
            second_half->next = temp1;
            first_half = temp1;
            second_half = temp2;
        }
    }
};
```

## Code (Java)

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
public class Solution {
    public void reorderList(ListNode head) {
        if (head == null || head.next == null) return;
        
        // Step 1: Find the middle of the list
        ListNode slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        
        // Step 2: Split the list into two halves
        ListNode second_half = slow.next;
        slow.next = null;
        
        // Step 3: Reverse the second half
        ListNode prev = null, current = second_half, next_node = null;
        while (current != null) {
            next_node = current.next;
            current.next = prev;
            prev = current;
            current = next_node;
        }
        second_half = prev;
        
        // Step 4: Merge the two halves alternately
        ListNode first_half = head;
        while (second_half != null) {
            ListNode temp1 = first_half.next;
            ListNode temp2 = second_half.next;
            first_half.next = second_half;
            second_half.next = temp1;
            first_half = temp1;
            second_half = temp2;
        }
    }
}
```

## Code (Python)

```python
# Definition for singly-linked list.
# class ListNode:
#    def __init__(self, x):
#        self.val = x
#        self.next = None

class Solution:
    # @param A : head node of linked list
    # @return the head node in the linked list
    def reorderList(self, A):
        if not A or not A.next:
            return A
        
        # Step 1: Find the middle of the list
        slow = fast = A
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
        
        # Step 2: Split the list into two halves
        second_half = slow.next
        slow.next = None
        
        # Step 3: Reverse the second half
        prev = None
        current = second_half
        while current:
            next_node = current.next
            current.next = prev
            prev = current
            current = next_node
        second_half = prev
        
        # Step 4: Merge the two halves alternately
        first_half = A
        while second_half:
            temp1 = first_half.next
            temp2 = second_half.next
            first_half.next = second_half
            second_half.next = temp1
            first_half = temp1
            second_half = temp2
        
        return A
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
