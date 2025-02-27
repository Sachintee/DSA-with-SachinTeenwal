---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Stack
---

# 🚀 _Day 58. Get Min from Stack_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/stack-gfg-160/problem/get-minimum-element-from-stack)  

## 💡 **Problem Description:**

Implement a stack that supports the following operations in **O(1) time**:  

## Code(C++)
```cpp
class Solution {
    stack<int> s, minStack;
public:
    void push(int x) {
        s.push(x);
        if (minStack.empty() || x <= minStack.top()) minStack.push(x);
    }

    void pop() {
        if (s.empty()) return;
        if (s.top() == minStack.top()) minStack.pop();
        s.pop();
    }

    int peek() {
        return s.empty() ? -1 : s.top();
    }

    int getMin() {
        return minStack.empty() ? -1 : minStack.top();
    }
};
```

## Code (Java)

```java
class Solution {
    private Stack<Integer> s = new Stack<>();
    private Stack<Integer> minStack = new Stack<>();
    public void push(int x) {
        s.push(x);
        if (minStack.isEmpty() || x <= minStack.peek()) {
            minStack.push(x);
        }
    }
    public void pop() {
        if (!s.isEmpty()) {
            if (s.peek().equals(minStack.peek())) {
                minStack.pop();
            }
            s.pop();
        }
    }
    public int peek() {
        return s.isEmpty() ? -1 : s.peek();
    }
    public int getMin() {
        return minStack.isEmpty() ? -1 : minStack.peek();
    }
}
```

## Code (Python)

```python
class Solution:
    def __init__(self):
        self.s, self.m = [], []

    def push(self, x):
        self.s.append(x)
        self.m.append(x if not self.m else min(x, self.m[-1]))

    def pop(self):
        if self.s: self.s.pop(), self.m.pop()

    def peek(self):
        return -1 if not self.s else self.s[-1]

    def getMin(self):
        return -1 if not self.m else self.m[-1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
