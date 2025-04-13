--- ❤️ ---

# 🚀 _Day 103. Partition List_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/partition-list/)

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
    ListNode* partition(ListNode* A, int B) {
        ListNode less_dummy(0); // Dummy node for nodes less than B
        ListNode* less_ptr = &less_dummy;
        ListNode greater_equal_dummy(0); // Dummy node for nodes >= B
        ListNode* greater_equal_ptr = &greater_equal_dummy;
        
        ListNode* current = A;
        while (current != nullptr) {
            if (current->val < B) {
                less_ptr->next = current;
                less_ptr = less_ptr->next;
            } else {
                greater_equal_ptr->next = current;
                greater_equal_ptr = greater_equal_ptr->next;
            }
            current = current->next;
        }
        
        // Connect the two lists
        less_ptr->next = greater_equal_dummy.next;
        greater_equal_ptr->next = nullptr; // Terminate the list
        
        return less_dummy.next;
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
class Solution {
    public ListNode partition(ListNode A, int B) {
        ListNode lessDummy = new ListNode(0); // Dummy node for nodes less than B
        ListNode lessPtr = lessDummy;
        ListNode greaterEqualDummy = new ListNode(0); // Dummy node for nodes >= B
        ListNode greaterEqualPtr = greaterEqualDummy;
        
        ListNode current = A;
        while (current != null) {
            if (current.val < B) {
                lessPtr.next = current;
                lessPtr = lessPtr.next;
            } else {
                greaterEqualPtr.next = current;
                greaterEqualPtr = greaterEqualPtr.next;
            }
            current = current.next;
        }
        
        // Connect the two lists
        lessPtr.next = greaterEqualDummy.next;
        greaterEqualPtr.next = null; // Terminate the list
        
        return lessDummy.next;
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
    # @param B : integer
    # @return the head node in the linked list
    def partition(self, A, B):
        less_head = ListNode(0)  # Dummy node for the list of nodes less than B
        less_ptr = less_head
        greater_equal_head = ListNode(0)  # Dummy node for the list of nodes >= B
        greater_equal_ptr = greater_equal_head
        
        current = A
        while current is not None:
            if current.val < B:
                less_ptr.next = current
                less_ptr = less_ptr.next
            else:
                greater_equal_ptr.next = current
                greater_equal_ptr = greater_equal_ptr.next
            current = current.next
        
        # Connect the two lists
        less_ptr.next = greater_equal_head.next
        greater_equal_ptr.next = None  # Important to avoid cycles
        
        return less_head.next
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
