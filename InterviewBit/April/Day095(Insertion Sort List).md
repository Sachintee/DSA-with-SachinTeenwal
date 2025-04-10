--- ❤️ ---

# 🚀 _Day 95. Insertion Sort List_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/insertion-sort-list/)

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
    ListNode* insertionSortList(ListNode* head) {
        if (!head || !head->next) {
            return head;
        }
        
        ListNode* dummy = new ListNode(0);
        dummy->next = head;
        ListNode* current = head;
        
        while (current && current->next) {
            if (current->val <= current->next->val) {
                current = current->next;
            } else {
                ListNode* to_insert = current->next;
                current->next = to_insert->next;
                
                ListNode* prev = dummy;
                while (prev->next && prev->next->val < to_insert->val) {
                    prev = prev->next;
                }
                
                to_insert->next = prev->next;
                prev->next = to_insert;
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
    public ListNode insertionSortList(ListNode head) {
        if (head == null || head.next == null) {
            return head;
        }
        
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode current = head;
        
        while (current != null && current.next != null) {
            if (current.val <= current.next.val) {
                current = current.next;
            } else {
                ListNode toInsert = current.next;
                current.next = toInsert.next;
                
                ListNode prev = dummy;
                while (prev.next != null && prev.next.val < toInsert.val) {
                    prev = prev.next;
                }
                
                toInsert.next = prev.next;
                prev.next = toInsert;
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
    def insertionSortList(self, A):
        if not A or not A.next:
            return A
        
        dummy = ListNode(0)
        dummy.next = A
        current = A
        
        while current and current.next:
            if current.val <= current.next.val:
                current = current.next
            else:
                # Extract the node to be inserted
                to_insert = current.next
                current.next = to_insert.next
                
                # Find the correct position to insert
                prev = dummy
                while prev.next and prev.next.val < to_insert.val:
                    prev = prev.next
                
                # Insert the node
                to_insert.next = prev.next
                prev.next = to_insert
        
        return dummy.next
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
