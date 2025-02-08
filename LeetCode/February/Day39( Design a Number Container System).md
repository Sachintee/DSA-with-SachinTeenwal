--- ❤️ ---

# 🚀 _Day 39.  Design a Number Container System_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/design-a-number-container-system/description/?envType=daily-question&envId=2025-02-08)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class NumberContainers {
public:
    NumberContainers() {
    }

    void change(int index, int number) {
        if (d.contains(index)) {
            int oldNumber = d[index];
            g[oldNumber].erase(index);
            if (g[oldNumber].empty()) {
                g.erase(oldNumber);
            }
        }
        d[index] = number;
        g[number].insert(index);
    }

    int find(int number) {
        return g.contains(number) ? *g[number].begin() : -1;
    }

private:
    unordered_map<int, int> d;
    unordered_map<int, set<int>> g;
};

/**
 * Your NumberContainers object will be instantiated and called as such:
 * NumberContainers* obj = new NumberContainers();
 * obj->change(index,number);
 * int param_2 = obj->find(number);
 */
```

## Code (Java)

```java
class NumberContainers {
    private Map<Integer, Integer> d = new HashMap<>();
    private Map<Integer, TreeSet<Integer>> g = new HashMap<>();

    public NumberContainers() {
    }

    public void change(int index, int number) {
        if (d.containsKey(index)) {
            int oldNumber = d.get(index);
            g.get(oldNumber).remove(index);
        }
        d.put(index, number);
        g.computeIfAbsent(number, k -> new TreeSet<>()).add(index);
    }

    public int find(int number) {
        var ids = g.get(number);
        return ids == null || ids.isEmpty() ? -1 : ids.first();
    }
}

/**
 * Your NumberContainers object will be instantiated and called as such:
 * NumberContainers obj = new NumberContainers();
 * obj.change(index,number);
 * int param_2 = obj.find(number);
 */
```

## Code (Python)

```python
class NumberContainers:

    def __init__(self):
        self.d = {}
        self.g = defaultdict(SortedSet)

    def change(self, index: int, number: int) -> None:
        if index in self.d:
            old_number = self.d[index]
            self.g[old_number].remove(index)
        self.d[index] = number
        self.g[number].add(index)

    def find(self, number: int) -> int:
        ids = self.g[number]
        return ids[0] if ids else -1


# Your NumberContainers object will be instantiated and called as such:
# obj = NumberContainers()
# obj.change(index,number)
# param_2 = obj.find(number)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
