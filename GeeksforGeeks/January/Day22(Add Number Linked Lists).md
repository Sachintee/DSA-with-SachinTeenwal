---
Difficulty: : Medium 
Source: 160 Days of Problem Solving  
Tags:
  - Linked-List
---

# 🚀 _Day 22. Add Number Linked Lists 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/linked-list-gfg-160/problem/add-two-numbers-represented-by-linked-lists)




## Code(C++)
```cpp
#include <iostream>
using namespace std;

// Node structure
struct Node {
    int data;
    Node* next;

    Node(int x) : data(x), next(NULL) {}
};

class Solution {
public:
    // Function to add two numbers represented by linked list
    Node* addTwoLists(Node* num1, Node* num2) {
        // Reverse both lists to simplify addition
        num1 = reverse(num1);
        num2 = reverse(num2);

        Node* sum = NULL;
        int carry = 0;

        while (num1 || num2 || carry) {
            int newVal = carry;

            if (num1) {
                newVal += num1->data;
                num1 = num1->next;
            }
            if (num2) {
                newVal += num2->data;
                num2 = num2->next;
            }

            carry = newVal / 10;
            newVal %= 10;

            Node* newNode = new Node(newVal);
            newNode->next = sum;
            sum = newNode;
        }

        return removeLeadingZeros(sum);
    }

private:
    // Function to reverse the linked list
    Node* reverse(Node* head) {
        Node* prev = NULL;
        Node* current = head;

        while (current) {
            Node* next = current->next;
            current->next = prev;
            prev = current;
            current = next;
        }

        return prev;
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
    // Function to add two numbers represented by linked lists
    public Node addTwoLists(Node num1, Node num2) {
        // Reverse both lists to simplify addition
        num1 = reverse(num1);
        num2 = reverse(num2);

        Node sum = null;
        int carry = 0;

        while (num1 != null || num2 != null || carry != 0) {
            int newVal = carry;

            if (num1 != null) {
                newVal += num1.data;
                num1 = num1.next;
            }
            if (num2 != null) {
                newVal += num2.data;
                num2 = num2.next;
            }

            carry = newVal / 10;
            newVal %= 10;

            Node newNode = new Node(newVal);
            newNode.next = sum;
            sum = newNode;
        }

        return removeLeadingZeros(sum);
    }

    // Function to reverse the linked list
    private Node reverse(Node head) {
        Node prev = null;
        Node current = head;

        while (current != null) {
            Node next = current.next;
            current.next = prev;
            prev = current;
            current = next;
        }

        return prev;
    }

    // Function to remove leading zeros from the result
    private Node removeLeadingZeros(Node head) {
        Node current = head;
        Node prev = null;

        while (current != null && current.data == 0) {
            prev = current;
            current = current.next;
            prev.next = null;
        }

        return (current != null) ? current : new Node(0);
    }
}
```

## Code (Python)

```python
''' Node for linked list:

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

'''
class Solution:
    #Function to add two numbers represented by linked list.
    def addTwoLists(self, num1, num2):
        # Reverse both lists to simplify addition.
        num1 = self.reverse(num1)
        num2 = self.reverse(num2)

        sum = None
        carry = 0

        while num1 or num2 or carry:
            newVal = carry

            if num1:
                newVal += num1.data
                num1 = num1.next
            if num2:
                newVal += num2.data
                num2 = num2.next

            carry = newVal // 10
            newVal %= 10

            newNode = Node(newVal)
            newNode.next = sum
            sum = newNode

        return self.removeLeadingZeros(sum)

    #Function to reverse the linked list.
    def reverse(self, head):
        prev = None
        current = head

        while current:
            next = current.next
            current.next = prev
            prev = current
            current = next

        return prev

    #Function to remove leading zeros from the result.
    def removeLeadingZeros(self, head):
        current = head
        prev = None

        while current and current.data == 0:
            prev = current
            current = current.next
            prev.next = None

        return current if current else Node(0)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>652</h4>
