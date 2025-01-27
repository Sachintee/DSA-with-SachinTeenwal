--- ❤️ ---
Difficulty: Hard
Source: 160 Days of Problem Solving  
Tags:
  - Linked-List
---

# 🚀 _Day 27. LRU Cache_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/linked-list-gfg-160/problem/lru-cache)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <unordered_map>

class Node {
public:
    int key, value;
    Node* prev;
    Node* next;

    Node(int k, int v) : key(k), value(v), prev(nullptr), next(nullptr) {}
};

class LRUCache {
private:
    int capacity;
    std::unordered_map<int, Node*> cache;
    Node* head;
    Node* tail;

    void remove(Node* node) {
        node->prev->next = node->next;
        node->next->prev = node->prev;
    }

    void add(Node* node) {
        node->next = head->next;
        node->prev = head;
        head->next->prev = node;
        head->next = node;
    }

public:
    LRUCache(int cap) : capacity(cap) {
        head = new Node(0, 0); // Dummy head node
        tail = new Node(0, 0); // Dummy tail node
        head->next = tail;
        tail->prev = head;
    }

    int get(int key) {
        if (cache.find(key) != cache.end()) {
            Node* node = cache[key];
            remove(node);   // Move the accessed node to the front
            add(node);
            return node->value;
        }
        return -1;
    }

    void put(int key, int value) {
        if (cache.find(key) != cache.end()) {
            remove(cache[key]);
        } else if (cache.size() == capacity) {
            Node* lru = tail->prev;  // Least recently used node
            remove(lru);
            cache.erase(lru->key);
            delete lru;
        }
        Node* newNode = new Node(key, value);
        cache[key] = newNode;
        add(newNode);
    }
};

```

## Code (Java)

```java
import java.util.HashMap;

class Node {
    int key, value;
    Node prev, next;

    Node(int key, int value) {
        this.key = key;
        this.value = value;
    }
}

class LRUCache {
    private final int capacity;
    private final HashMap<Integer, Node> cache;
    private final Node head, tail;

    public LRUCache(int cap) {
        this.capacity = cap;
        this.cache = new HashMap<>();
        this.head = new Node(0, 0); // Dummy head node
        this.tail = new Node(0, 0); // Dummy tail node
        head.next = tail;
        tail.prev = head;
    }

    private void remove(Node node) {
        node.prev.next = node.next;
        node.next.prev = node.prev;
    }

    private void add(Node node) {
        node.next = head.next;
        node.prev = head;
        head.next.prev = node;
        head.next = node;
    }

    public int get(int key) {
        if (cache.containsKey(key)) {
            Node node = cache.get(key);
            remove(node);  // Move the accessed node to the front
            add(node);
            return node.value;
        }
        return -1;
    }

    public void put(int key, int value) {
        if (cache.containsKey(key)) {
            remove(cache.get(key));
        } else if (cache.size() == capacity) {
            Node lru = tail.prev;  // Least recently used node
            remove(lru);
            cache.remove(lru.key);
        }
        Node newNode = new Node(key, value);
        cache.put(key, newNode);
        add(newNode);
    }
}

```

## Code (Python)

```python
# design the class in the most optimal way
class Node:
    def __init__(self, key, value):
        self.key = key
        self.value = value
        self.prev = None
        self.next = None

class LRUCache:
 
    def __init__(self, cap):
        """
        Initialize the LRUCache with a given capacity.
        """
        self.capacity = cap
        self.cache = {}  # Hashmap to store key-node pairs
        self.head = Node(0, 0)  # Dummy head node
        self.tail = Node(0, 0)  # Dummy tail node
        self.head.next = self.tail
        self.tail.prev = self.head

    def _remove(self, node):
        """
        Remove a node from the doubly linked list.
        """
        prev_node = node.prev
        next_node = node.next
        prev_node.next = next_node
        next_node.prev = prev_node

    def _add(self, node):
        """
        Add a node right after the head.
        """
        next_node = self.head.next
        self.head.next = node
        node.prev = self.head
        node.next = next_node
        next_node.prev = node

    def get(self, key):
        """
        Return the value of the key if it exists in the cache; otherwise, return -1.
        """
        if key in self.cache:
            node = self.cache[key]
            self._remove(node)  # Move the accessed node to the head (most recently used)
            self._add(node)
            return node.value
        return -1

    def put(self, key, value):
        """
        Add a key-value pair to the cache. If the cache exceeds capacity,
        remove the least recently used item.
        """
        if key in self.cache:
            # If the key exists, remove the old node
            self._remove(self.cache[key])
        elif len(self.cache) == self.capacity:
            # If at capacity, remove the least recently used item (tail's previous node)
            lru_node = self.tail.prev
            self._remove(lru_node)
            del self.cache[lru_node.key]

        # Add the new node to the cache and the linked list
        new_node = Node(key, value)
        self.cache[key] = new_node
        self._add(new_node)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>758</h4>
