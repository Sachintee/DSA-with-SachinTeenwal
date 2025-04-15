--- ❤️ ---

# 🚀 _Day 105. Swap List Nodes in pairs_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/swap-list-nodes-in-pairs/)

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
    ListNode* swapPairs(ListNode* A) {
        ListNode dummy(0);
        dummy.next = A;
        ListNode* current = &dummy;
        
        while (current->next && current->next->next) {
            ListNode* first_node = current->next;
            ListNode* second_node = current->next->next;
            
            // Swapping
            first_node->next = second_node->next;
            second_node->next = first_node;
            current->next = second_node;
            
            // Move to the next pair
            current = first_node;
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
    public ListNode swapPairs(ListNode A) {
        ListNode dummy = new ListNode(0);
        dummy.next = A;
        ListNode current = dummy;
        
        while (current.next != null && current.next.next != null) {
            ListNode first_node = current.next;
            ListNode second_node = current.next.next;
            
            // Swapping
            first_node.next = second_node.next;
            second_node.next = first_node;
            current.next = second_node;
            
            // Move to the next pair
            current = first_node;
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
    def swapPairs(self, A):
        dummy = ListNode(0)
        dummy.next = A
        current = dummy
        
        while current.next and current.next.next:
            first_node = current.next
            second_node = current.next.next
            
            # Swapping
            first_node.next = second_node.next
            second_node.next = first_node
            current.next = second_node
            
            # Move to the next pair
            current = first_node
        
        return dummy.next
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
