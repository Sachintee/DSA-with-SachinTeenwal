--- ❤️ ---

# 🚀 _Day 106. Add Two Numbers as Lists_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/add-two-numbers-as-lists/)

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
    ListNode* addTwoNumbers(ListNode* A, ListNode* B) {
        ListNode dummy(0);
        ListNode* current = &dummy;
        int carry = 0;
        
        while (A != nullptr || B != nullptr || carry != 0) {
            int sum_val = carry;
            if (A != nullptr) {
                sum_val += A->val;
                A = A->next;
            }
            if (B != nullptr) {
                sum_val += B->val;
                B = B->next;
            }
            carry = sum_val / 10;
            current->next = new ListNode(sum_val % 10);
            current = current->next;
        }
        
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
class Solution {
    public ListNode addTwoNumbers(ListNode A, ListNode B) {
        ListNode dummy = new ListNode(0);
        ListNode current = dummy;
        int carry = 0;
        
        while (A != null || B != null || carry != 0) {
            int sum_val = carry;
            if (A != null) {
                sum_val += A.val;
                A = A.next;
            }
            if (B != null) {
                sum_val += B.val;
                B = B.next;
            }
            carry = sum_val / 10;
            current.next = new ListNode(sum_val % 10);
            current = current.next;
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
    # @param B : head node of linked list
    # @return the head node in the linked list
    def addTwoNumbers(self, A, B):
        dummy = ListNode(0)
        current = dummy
        carry = 0
        
        while A is not None or B is not None or carry != 0:
            sum_val = carry
            if A is not None:
                sum_val += A.val
                A = A.next
            if B is not None:
                sum_val += B.val
                B = B.next
            carry = sum_val // 10
            current.next = ListNode(sum_val % 10)
            current = current.next
        
        return dummy.next
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
