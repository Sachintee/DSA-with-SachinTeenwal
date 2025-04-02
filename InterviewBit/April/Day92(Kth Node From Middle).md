--- ❤️ ---

# 🚀 _Day 92. Kth Node From Middle_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/kth-node-from-middle/)

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
    int solve(ListNode* A, int B) {
        // Step 1: Find the length of the linked list
        int length = 0;
        ListNode* current = A;
        while (current != nullptr) {
            length++;
            current = current->next;
        }
        
        // Step 2: Determine the middle position (1-based)
        int middle_pos = (length / 2) + 1;
        
        // Step 3: Calculate the target position (0-based)
        int target_pos = middle_pos - 1 - B;
        
        // Step 4: Check if the target position is valid
        if (target_pos < 0) {
            return -1;
        }
        
        // Step 5: Traverse to the target position
        current = A;
        for (int i = 0; i < target_pos; ++i) {
            current = current->next;
        }
        
        return current->val;
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
    public int solve(ListNode A, int B) {
        // Step 1: Find the length of the linked list
        int length = 0;
        ListNode current = A;
        while (current != null) {
            length++;
            current = current.next;
        }
        
        // Step 2: Determine the middle position (1-based)
        int middlePos = (length / 2) + 1;
        
        // Step 3: Calculate the target position (0-based)
        int targetPos = middlePos - 1 - B;
        
        // Step 4: Check if the target position is valid
        if (targetPos < 0) {
            return -1;
        }
        
        // Step 5: Traverse to the target position
        current = A;
        for (int i = 0; i < targetPos; i++) {
            current = current.next;
        }
        
        return current.val;
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
    # @return an integer
    def solve(self, A, B):
        # Step 1: Find the length of the linked list
        length = 0
        current = A
        while current is not None:
            length += 1
            current = current.next
        
        # Step 2: Determine the middle position (1-based)
        middle_pos = (length // 2) + 1
        
        # Step 3: Calculate the target position (1-based)
        target_pos = middle_pos - 1 - B
        
        # Step 4: Check if the target position is valid
        if target_pos < 0:
            return -1
        
        # Step 5: Traverse to the target position
        current = A
        for _ in range(target_pos):
            current = current.next
        
        return current.val
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
