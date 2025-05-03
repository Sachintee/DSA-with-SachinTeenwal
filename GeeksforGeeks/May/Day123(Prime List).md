# *123. Prime List*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/prime-list--170646/1)

## **🧩 Problem Description**

You are given the head of a singly linked list. Your task is to replace the value of each node with the nearest prime number.

If multiple prime numbers are equidistant from the current value, choose the smaller one. Return the head of the updated linked list.


## Code(C++)
```cpp
class Solution {
public:
    Node* primeList(Node* h) {
        int m = 0;
        for (auto p = h; p; p = p->next) m = max(m, p->val);
        vector<char> s(2*m+1, 1);
        s[0] = s[1] = 0;
        for (int i = 2; i*i <= 2*m; ++i)
            if (s[i])
                for (int j = i*i; j <= 2*m; j += i)
                    s[j] = 0;
        for (auto p = h; p; p = p->next) {
            int x = p->val, d = 0;
            while (1) {
                if (x-d > 1 && s[x-d]) { p->val = x-d; break; }
                if (x+d <= 2*m && s[x+d]) { p->val = x+d; break; }
                ++d;
            }
        }
        return h;
    }
};
```

## Code (Java)

```java
class Solution {
    Node primeList(Node h) {
        int m = 0;
        for (Node p = h; p != null; p = p.next) m = Math.max(m, p.val);
        boolean[] s = new boolean[2*m+1];
        Arrays.fill(s, true);
        s[0] = s[1] = false;
        for (int i = 2; i*i <= 2*m; i++)
            if (s[i])
                for (int j = i*i; j <= 2*m; j += i) s[j] = false;
        for (Node p = h; p != null; p = p.next) {
            int x = p.val, d = 0;
            while (true) {
                if (x-d > 1 && s[x-d]) { p.val = x-d; break; }
                if (x+d <= 2*m && s[x+d]) { p.val = x+d; break; }
                d++;
            }
        }
        return h;
    }
}
```

## Code (Python)

```python
class Solution:
    def primeList(self, h):
        m = 0; p = h
        while p: m = max(m, p.val); p = p.next
        s = [1]*(2*m+1); s[0] = s[1] = 0
        for i in range(2, int((2*m)**0.5)+1):
            if s[i]: s[i*i:2*m+1:i] = [0]*len(range(i*i, 2*m+1, i))
        p = h
        while p:
            x, d = p.val, 0
            while 1:
                if x-d > 1 and s[x-d]: p.val = x-d; break
                if x+d <= 2*m and s[x+d]: p.val = x+d; break
                d += 1
            p = p.next
        return h
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
