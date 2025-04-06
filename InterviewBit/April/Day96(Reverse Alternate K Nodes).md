--- ❤️ ---

# 🚀 _Day 96. Reverse Alternate K Nodes_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/reverse-alternate-k-nodes/)

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
    ListNode* solve(ListNode* A, int B) {
        if (!A || B == 1) {
            return A;
        }
        
        ListNode* dummy = new ListNode(0);
        dummy->next = A;
        ListNode* prev = dummy;
        ListNode* current = A;
        bool reverseFlag = true;
        
        while (current) {
            if (reverseFlag) {
                ListNode* segmentStart = current;
                for (int i = 0; i < B - 1 && current->next; ++i) {
                    current = current->next;
                }
                ListNode* nextSegment = current->next;
                current->next = nullptr;
                ListNode* reversedSegment = reverseList(segmentStart);
                prev->next = reversedSegment;
                segmentStart->next = nextSegment;
                prev = segmentStart;
                current = nextSegment;
            } else {
                for (int i = 0; i < B && current; ++i) {
                    prev = current;
                    current = current->next;
                }
            }
            reverseFlag = !reverseFlag;
        }
        
        return dummy->next;
    }
    
    ListNode* reverseList(ListNode* head) {
        ListNode* prev = nullptr;
        ListNode* current = head;
        while (current) {
            ListNode* nextNode = current->next;
            current->next = prev;
            prev = current;
            current = nextNode;
        }
        return prev;
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
    public ListNode solve(ListNode A, int B) {
        if (A == null || B == 1) {
            return A;
        }
        
        ListNode dummy = new ListNode(0);
        dummy.next = A;
        ListNode prev = dummy;
        ListNode current = A;
        boolean reverseFlag = true;
        
        while (current != null) {
            if (reverseFlag) {
                ListNode segmentStart = current;
                for (int i = 0; i < B - 1 && current.next != null; i++) {
                    current = current.next;
                }
                ListNode nextSegment = current.next;
                current.next = null;
                ListNode reversedSegment = reverseList(segmentStart);
                prev.next = reversedSegment;
                segmentStart.next = nextSegment;
                prev = segmentStart;
                current = nextSegment;
            } else {
                for (int i = 0; i < B && current != null; i++) {
                    prev = current;
                    current = current.next;
                }
            }
            reverseFlag = !reverseFlag;
        }
        
        return dummy.next;
    }
    
    private ListNode reverseList(ListNode head) {
        ListNode prev = null;
        ListNode current = head;
        while (current != null) {
            ListNode nextNode = current.next;
            current.next = prev;
            prev = current;
            current = nextNode;
        }
        return prev;
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
    def solve(self, A, B):
        if not A or B == 1:
            return A
        
        dummy = ListNode(0)
        dummy.next = A
        prev = dummy
        current = A
        reverse_flag = True
        
        while current:
            if reverse_flag:
                # Store the start of the segment to be reversed
                segment_start = current
                # Traverse B nodes
                for _ in range(B - 1):
                    if current.next:
                        current = current.next
                    else:
                        break
                # The node after the segment
                next_segment = current.next
                # Disconnect the segment
                current.next = None
                # Reverse the segment
                reversed_segment = self.reverse_list(segment_start)
                # Reconnect the reversed segment
                prev.next = reversed_segment
                segment_start.next = next_segment
                # Move prev to the end of the reversed segment
                prev = segment_start
                current = next_segment
            else:
                # Skip B nodes without reversing
                for _ in range(B):
                    if current:
                        prev = current
                        current = current.next
                    else:
                        break
            # Toggle the flag for the next segment
            reverse_flag = not reverse_flag
        
        return dummy.next
    
    def reverse_list(self, head):
        prev = None
        current = head
        while current:
            next_node = current.next
            current.next = prev
            prev = current
            current = next_node
        return prev
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
