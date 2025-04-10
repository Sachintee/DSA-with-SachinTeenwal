--- ❤️ ---

# 🚀 _Day 93. Remove Duplicates from Sorted List II_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/remove-duplicates-from-sorted-list-ii/)

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
    ListNode* deleteDuplicates(ListNode* head) {
        if (!head || !head->next) {
            return head;
        }
        
        ListNode* dummy = new ListNode(0);
        dummy->next = head;
        ListNode* prev = dummy;
        ListNode* current = head;
        
        while (current) {
            if (current->next && current->val == current->next->val) {
                int val = current->val;
                while (current && current->val == val) {
                    current = current->next;
                }
                prev->next = current;
            } else {
                prev = current;
                current = current->next;
            }
        }
        
        return dummy->next;
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
    public ListNode deleteDuplicates(ListNode head) {
        if (head == null || head.next == null) {
            return head;
        }
        
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode prev = dummy;
        ListNode current = head;
        
        while (current != null) {
            if (current.next != null && current.val == current.next.val) {
                int val = current.val;
                while (current != null && current.val == val) {
                    current = current.next;
                }
                prev.next = current;
            } else {
                prev = current;
                current = current.next;
            }
        }
        
        return dummy.next;
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
    def deleteDuplicates(self, A):
        if not A or not A.next:
            return A
        
        dummy = ListNode(0)
        dummy.next = A
        prev = dummy
        current = A
        
        while current:
            if current.next and current.val == current.next.val:
                val = current.val
                while current and current.val == val:
                    current = current.next
                prev.next = current
            else:
                prev = current
                current = current.next
        
        return dummy.next
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
