---
title: "🔗 Find Length of Loop | GFG Solution 🎯"
keywords🏷️: ["🔗 linked list", "🔄 cycle detection", "🏃‍♂️ floyd's algorithm", "📍 two pointers", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Find Length of Loop problem: detect and count nodes in a linked list loop using Floyd's Cycle Detection Algorithm (Tortoise and Hare). 🚀"
date: 📅 2025-09-06
---

# *249. Find Length of Loop*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/find-length-of-loop/1)

## **🧩 Problem Description**

Given the head of a linked list, determine whether the list contains a loop. If a loop is present, return the **number of nodes in the loop**, otherwise return **0**.

**Note:** Internally, pos(1 based index) is used to denote the position of the node that tail's next pointer is connected to. If pos = 0, it means the last node points to null, indicating there is no loop. Note that pos is not passed as a parameter.


## Code(C++)
```cpp
class Solution {
public:
    int lengthOfLoop(Node* head) {
        Node *s = head, *f = head;
        while (f && f->next) {
            s = s->next;
            f = f->next->next;
            if (s == f) {
                int cnt = 1;
                while (s->next != f) s = s->next, cnt++;
                return cnt;
            }
        }
        return 0;
    }
};
```

## Code (Java)

```java
class Solution {
    public int lengthOfLoop(Node head) {
        Node s = head, f = head;
        while (f != null && f.next != null) {
            s = s.next;
            f = f.next.next;
            if (s == f) {
                int cnt = 1;
                while (s.next != f) {
                    s = s.next;
                    cnt++;
                }
                return cnt;
            }
        }
        return 0;
    }
}
```

## Code (Python)

```python
class Solution:
    def lengthOfLoop(self, head):
        s, f = head, head
        while f and f.next:
            s, f = s.next, f.next.next
            if s == f:
                cnt = 1
                while s.next != f:
                    s, cnt = s.next, cnt + 1
                return cnt
        return 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
