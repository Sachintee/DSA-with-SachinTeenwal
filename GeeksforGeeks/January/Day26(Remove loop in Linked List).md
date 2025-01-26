--- ❤️ ---
Difficulty: Medium
Source: 160 Days of Problem Solving  
Tags:
  - Linked-List
---

# 🚀 _Day 26. Remove loop in Linked List_ 🧠

Given the head of a linked list that may contain a loop. 
A loop means that the last node of the linked list is connected back to a node in the same list. The task is to remove the loop from the linked list (if it exists).

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/linked-list-gfg-160/problem/remove-loop-in-linked-list)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    void removeLoop(Node* head) {
        Node* slow = head;
        Node* fast = head;

        // Detect loop using Floyd’s cycle detection algorithm
        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;

            if (slow == fast) break;
        }

        // If no loop is detected
        if (!fast || !fast->next) return;

        // Move `slow` to head and find the start of the loop
        slow = head;
        while (slow != fast) {
            slow = slow->next;
            fast = fast->next;
        }

        // Move `fast` to the last node in the loop
        while (fast->next != slow) {
            fast = fast->next;
        }

        // Break the loop
        fast->next = nullptr;
    }
};

```

## Code (Java)

```java
class Solution {
    public void removeLoop(Node head) {
        Node slow = head;
        Node fast = head;

        // Detect loop using Floyd's cycle detection algorithm
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;

            if (slow == fast) break;
        }

        // If no loop is detected
        if (fast == null || fast.next == null) return;

        // Move `slow` to head and find the start of the loop
        slow = head;
        while (slow != fast) {
            slow = slow.next;
            fast = fast.next;
        }

        // Move `fast` to the last node in the loop
        while (fast.next != slow) {
            fast = fast.next;
        }

        // Break the loop
        fast.next = null;
    }
}

```

## Code (Python)

```python

class Solution:
    #Function to remove a loop in the linked list.
    def removeLoop(self, head):
        # code here
        slow, fast = head, head
        while fast and fast.next and (slow := slow.next) != (fast := fast.next.next): pass
        if not fast or not fast.next: return
        slow = head
        while slow != fast: slow, fast = slow.next, fast.next
        while fast.next != slow: fast = fast.next
        fast.next = None


```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>651</h4>
