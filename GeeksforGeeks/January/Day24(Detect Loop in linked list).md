--- ❤️ ---
Difficulty: Medium
Source: 160 Days of Problem Solving  
Tags:
  - Linked-List
---

# 🚀 _Day 24. Detect Loop in linked list_ 🧠

You are given the head of a singly linked list. Your task is to determine if the linked list contains a loop. 
A loop exists in a linked list if the next pointer of the last node points to any other node in the list (including itself), rather than being null.

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/linked-list-gfg-160/problem/detect-loop-in-linked-list)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <unordered_set>
using namespace std;

// Node class
class Node {
public:
    int data;
    Node* next;

    Node(int val) { // Constructor
        data = val;
        next = nullptr;
    }
};

class Solution {
public:
    // Function to check if the linked list has a loop
    bool detectLoop(Node* head) {
        unordered_set<Node*> visited;

        while (head != nullptr) {
            // If the node is already in the set, a loop is detected
            if (visited.find(head) != visited.end()) {
                return true;
            }
            // Add the current node to the set
            visited.insert(head);
            head = head->next;
        }
        return false;
    }
};

```

## Code (Java)

```java
import java.util.HashSet;

class Node {
    int data;
    Node next;

    Node(int data) { // Constructor
        this.data = data;
        this.next = null;
    }
}

class Solution {
    // Function to check if the linked list has a loop
    public boolean detectLoop(Node head) {
        HashSet<Node> visited = new HashSet<>();

        while (head != null) {
            // If the node is already in the set, a loop is detected
            if (visited.contains(head)) {
                return true;
            }
            // Add the current node to the set
            visited.add(head);
            head = head.next;
        }
        return false;
    }
}

```

## Code (Python)

```python

class Solution:
    #Function to check if the linked list has a loop.
    def detectLoop(self, head):
        #code here
        st = set()
        
        while head is not None :
            
            if head in st :
                return True 
                
            st.add(head)
            head = head.next 
    
        return False 

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>736</h4>
