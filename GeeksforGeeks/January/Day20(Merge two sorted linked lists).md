---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Linked-List
---

# 🚀 _Day 20.Merge two sorted linked lists_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/linked-list-gfg-160/problem/merge-two-sorted-linked-lists)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

// Node structure
struct Node {
    int data;
    Node* next;

    Node(int val) {
        data = val;
        next = nullptr;
    }
};

class Solution {
public:
    Node* sortedMerge(Node* head1, Node* head2) {
        Node dummy(-1); // Dummy node to simplify operations
        Node* res = &dummy;

        Node* h1 = head1;
        Node* h2 = head2;

        // Merge the two lists
        while (h1 != nullptr && h2 != nullptr) {
            if (h1->data < h2->data) {
                res->next = h1;
                h1 = h1->next;
            } else {
                res->next = h2;
                h2 = h2->next;
            }
            res = res->next;
        }

        // Attach the remaining elements
        if (h1 != nullptr) {
            res->next = h1;
        }
        if (h2 != nullptr) {
            res->next = h2;
        }

        return dummy.next;
    }
};

// Helper functions for testing
void printList(Node* head) {
    while (head != nullptr) {
        cout << head->data << " ";
        head = head->next;
    }
    cout << endl;
}

int main() {
    Node* head1 = new Node(1);
    head1->next = new Node(3);
    head1->next->next = new Node(5);

    Node* head2 = new Node(2);
    head2->next = new Node(4);
    head2->next->next = new Node(6);

    Solution sol;
    Node* result = sol.sortedMerge(head1, head2);

    printList(result); // Output: 1 2 3 4 5 6

    return 0;
}
```

## Code (Java)

```java
class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

class Solution {
    public Node sortedMerge(Node head1, Node head2) {
        Node dummy = new Node(-1); // Dummy node to simplify operations
        Node res = dummy;

        Node h1 = head1;
        Node h2 = head2;

        // Merge the two lists
        while (h1 != null && h2 != null) {
            if (h1.data < h2.data) {
                res.next = h1;
                h1 = h1.next;
            } else {
                res.next = h2;
                h2 = h2.next;
            }
            res = res.next;
        }

        // Attach the remaining elements
        if (h1 != null) {
            res.next = h1;
        }
        if (h2 != null) {
            res.next = h2;
        }

        return dummy.next;
    }

    // Helper function to print the list
    public void printList(Node head) {
        while (head != null) {
            System.out.print(head.data + " ");
            head = head.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        Node head1 = new Node(1);
        head1.next = new Node(3);
        head1.next.next = new Node(5);

        Node head2 = new Node(2);
        head2.next = new Node(4);
        head2.next.next = new Node(6);

        Solution sol = new Solution();
        Node result = sol.sortedMerge(head1, head2);

        sol.printList(result); // Output: 1 2 3 4 5 6
    }
}
```

## Code (Python)

```python
'''
# Node Class
class Node:
    def __init__(self, data):   # data -> value stored in node
        self.data = data
        self.next = None

'''
class Solution:
    def sortedMerge(self,head1, head2):
        # code here
        # More optimize way
        h1 = head1
        h2 = head2
        res = Node(-1)
        r = res
        while h1 != None and h2 != None:
            if h1.data < h2.data:
                res.next = h1
                res = res.next
                h1 = h1.next
            else:
                res.next = h2
                res = res.next
                h2 = h2.next
                
        if h1 is None:
            res.next = h2
        if h2 is None:
            res.next = h1
            
        return r.next
        # lst1 , lst2 = [] , []
        # curr = head1
        # while curr:
        #     lst1.append(curr.data)
        #     curr = curr.next
            
        # curr = head2
        # while curr:
        #     lst2.append(curr.data)
        #     curr= curr.next
            
        # ans = lst1 + lst2
        # ans.sort()
        # print(ans)
        # curr = head1
        # for x in ans:
        #     curr.data = x
        #     curr = curr.next
            
        # while curr:
        #     next_node = curr.next
        #     curr.next = None
        #     curr = next_node
            
        # return head1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>698</h4>
