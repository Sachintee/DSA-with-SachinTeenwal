# *120. Find Length of Loop*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/find-length-of-loop/1)


## **🧩 Problem Description**

Given the head of a linked list, determine whether the list contains a loop. If a loop is present, return the number of nodes in the loop; otherwise, return `0`.


## Code(C++)
```cpp
class Solution {
  public:
    int countNodesinLoop(Node *head) {
        Node *slow = head, *fast = head;
        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;
            if (slow == fast) {
                int c = 1;
                while ((fast = fast->next) != slow) c++;
                return c;
            }
        }
        return 0;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countNodesinLoop(Node head) {
        Node slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) {
                int c = 1;
                while ((fast = fast.next) != slow) c++;
                return c;
            }
        }
        return 0;
    }
}
```

## Code (Python)

```python
class Solution:
    def countNodesInLoop(self, head):
        slow = fast = head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
            if slow == fast:
                c = 1
                while (fast := fast.next) != slow:
                    c += 1
                return c
        return 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
