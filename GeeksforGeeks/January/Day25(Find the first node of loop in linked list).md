--- ❤️ ---
Difficulty: Easy
Source: 160 Days of Problem Solving  
Tags:
  - Linked-List
---

# 🚀 _Day 25. Find the first node of loop in linked list_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/linked-list-gfg-160/problem/find-the-first-node-of-loop-in-linked-list--170645)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Node {
public:
    int data;
    Node* next;

    Node(int data) { // Constructor
        this->data = data;
        this->next = nullptr;
    }
};

class Solution {
public:
    Node* findFirstNode(Node* head) {
        Node* slow = head;
        Node* fast = head;

        // Detect if a cycle exists
        while (fast != nullptr && fast->next != nullptr) {
            fast = fast->next->next;
            slow = slow->next;

            if (fast == slow) {
                break;
            }
        }

        // If no cycle, return null
        if (fast != slow) {
            return nullptr;
        }

        // Find the start of the loop
        slow = head;
        while (slow != fast) {
            fast = fast->next;
            slow = slow->next;
        }

        return slow;
    }
};

```

## Code (Java)

```java
class Node {
    int data;
    Node next;

    Node(int data) { // Constructor
        this.data = data;
        this.next = null;
    }
}

class Solution {
    public Node findFirstNode(Node head) {
        Node slow = head;
        Node fast = head;

        // Detect if a cycle exists
        while (fast != null && fast.next != null) {
            fast = fast.next.next;
            slow = slow.next;

            if (fast == slow) {
                break;
            }
        }

        // If no cycle, return null
        if (fast != slow) {
            return null;
        }

        // Find the start of the loop
        slow = head;
        while (slow != fast) {
            fast = fast.next;
            slow = slow.next;
        }

        return slow;
    }
}

```

## Code (Python)

```python

class Solution:
    def findFirstNode(self, head):
        slow = head
        fast = head
        
        while fast and fast.next:
            fast = fast.next.next
            slow = slow.next
            
            if fast == slow:
                break
        
        if fast != slow:
            return None
        
        slow = head
        while slow != fast:
            fast = fast.next
            slow = slow.next
        
        return slow

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>605</h4>
