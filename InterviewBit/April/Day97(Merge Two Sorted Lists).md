--- ❤️ ---

# 🚀 _Day 97. Merge Two Sorted Lists_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/merge-two-sorted-lists/)

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
    ListNode* mergeTwoLists(ListNode* A, ListNode* B) {
        ListNode dummy(0);
        ListNode* current = &dummy;
        
        while (A && B) {
            if (A->val < B->val) {
                current->next = A;
                A = A->next;
            } else {
                current->next = B;
                B = B->next;
            }
            current = current->next;
        }
        
        current->next = A ? A : B;
        return dummy.next;
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
    public ListNode mergeTwoLists(ListNode A, ListNode B) {
        ListNode dummy = new ListNode(0);
        ListNode current = dummy;
        
        while (A != null && B != null) {
            if (A.val < B.val) {
                current.next = A;
                A = A.next;
            } else {
                current.next = B;
                B = B.next;
            }
            current = current.next;
        }
        
        current.next = A != null ? A : B;
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
    # @param B : head node of linked list
    # @return the head node in the linked list
    def mergeTwoLists(self, A, B):
        dummy = ListNode(0)
        current = dummy
        
        while A and B:
            if A.val < B.val:
                current.next = A
                A = A.next
            else:
                current.next = B
                B = B.next
            current = current.next
        
        current.next = A if A else B
        return dummy.next
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
