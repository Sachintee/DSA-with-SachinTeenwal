---
Difficulty: Medium
Source: 160 Days of Problem Solving
Tags:
  - Trie
  - Design-Pattern
  - Advanced Data Structure
---

# 🚀 _Day 108. Implement Trie_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tries-gfg-160/problem/trie-insert-and-search0651)  

## 💡 **Problem Description:**

Implement the Trie data structure. You are given queries of the following three types:
- **Type 1**: Insert a word into the Trie.
- **Type 2**: Search whether a word exists in the Trie.
- **Type 3**: Check whether a word is a prefix of any word stored in the Trie.

## Code(C++)
```cpp
//  Fixed‐Array Trie (26 pointers per node)
class Trie {
    struct N { N* c[26] = {}; bool e = 0; }*r = new N;
public:
    void insert(string &w) {
        auto n = r;
        for (char ch : w) n = n->c[ch - 'a'] ?: (n->c[ch - 'a'] = new N);
        n->e = 1;
    }
    bool search(string &w) {
        auto n = r;
        for (char ch : w) if (!(n = n->c[ch - 'a'])) return 0;
        return n->e;
    }
    bool isPrefix(string &w) {
        auto n = r;
        for (char ch : w) if (!(n = n->c[ch - 'a'])) return 0;
        return 1;
    }
};
```

## Code (Java)

```java
class Trie {
    class N { N[] c = new N[26]; boolean e; }
    N r = new N();
    public void insert(String w) {
        N n = r;
        for (char ch : w.toCharArray())
            n = n.c[ch - 'a'] != null ? n.c[ch - 'a'] : (n.c[ch - 'a'] = new N());
        n.e = true;
    }
    public boolean search(String w) {
        N n = r;
        for (char ch : w.toCharArray())
            if ((n = n.c[ch - 'a']) == null) return false;
        return n.e;
    }
    public boolean isPrefix(String w) {
        N n = r;
        for (char ch : w.toCharArray())
            if ((n = n.c[ch - 'a']) == null) return false;
        return true;
    }
}
```

## Code (Python)

```python
class Trie:
    class N:
        def __init__(self): self.c, self.e = [None]*26, 0
    def __init__(self): self.r = self.N()
    def insert(self, w):
        n = self.r
        for ch in w:
            i = ord(ch)-97
            n.c[i] = n.c[i] or self.N()
            n = n.c[i]
        n.e = 1
    def search(self, w):
        n = self.r
        for ch in w:
            i = ord(ch)-97
            if not n.c[i]: return 0
            n = n.c[i]
        return n.e
    def isPrefix(self, w):
        n = self.r
        for ch in w:
            i = ord(ch)-97
            if not n.c[i]: return 0
            n = n.c[i]
        return 1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
