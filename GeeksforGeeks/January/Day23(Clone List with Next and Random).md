---
Difficulty: Hard
Source: 160 Days of Problem Solving  
Tags:
  - Linked-List
---

# 🚀 _Day 23. Clone List with Next and Random_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/linked-list-gfg-160/problem/clone-a-linked-list-with-next-and-random-pointer)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <unordered_map>

// Definition for a Node
class Node {
public:
    int data;
    Node* next;
    Node* random;
    Node(int x) {
        data = x;
        next = nullptr;
        random = nullptr;
    }
};

class Solution {
public:
    Node* cloneLinkedList(Node* head) {
        if (!head) return nullptr;

        std::unordered_map<Node*, Node*> mp;
        Node* curr = head;

        // Create a map of original nodes to their clones
        while (curr) {
            mp[curr] = new Node(curr->data);
            curr = curr->next;
        }

        // Set next and random pointers for cloned nodes
        curr = head;
        while (curr) {
            mp[curr]->next = mp[curr->next];
            mp[curr]->random = mp[curr->random];
            curr = curr->next;
        }

        return mp[head];
    }
};
```

## Code (Java)

```java
import java.util.HashMap;

// Definition for a Node
class Node {
    int data;
    Node next;
    Node random;
    Node(int x) {
        data = x;
        next = null;
        random = null;
    }
}

class Solution {
    public Node cloneLinkedList(Node head) {
        if (head == null) return null;

        HashMap<Node, Node> map = new HashMap<>();
        Node curr = head;

        // Create a map of original nodes to their clones
        while (curr != null) {
            map.put(curr, new Node(curr.data));
            curr = curr.next;
        }

        // Set next and random pointers for cloned nodes
        curr = head;
        while (curr != null) {
            Node clonedNode = map.get(curr);
            clonedNode.next = map.get(curr.next);
            clonedNode.random = map.get(curr.random);
            curr = curr.next;
        }

        return map.get(head);
    }
}
```

## Code (Python)

```python
# Link list Node
# class Node:

#     def __init__(self, x):
#         self.data = x
#         self.next = None
#         self.random = None
        
class Solution:
    def cloneLinkedList(self, head):
        # code here
        mp = {}
        curr = head
        while curr is not None:
            mp[curr] = Node(curr.data)
            curr = curr.next
        curr = head
        while curr is not None:
            new_node = mp[curr]
            new_node.next = mp.get(curr.next)
            new_node.random = mp.get(curr.random)
            curr = curr.next
        return mp.get(head)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>701</h4>
