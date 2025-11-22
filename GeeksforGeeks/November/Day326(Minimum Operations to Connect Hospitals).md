--- ❤️ ---

# 🚀 _Day 326. Minimum Operations to Connect Hospitals_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/minimize-connections/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> parent, rankv;

    int findp(int x) {
        if (parent[x] == x) return x;
        return parent[x] = findp(parent[x]);
    }

    void unite(int a, int b) {
        a = findp(a);
        b = findp(b);
        if (a == b) return;
        if (rankv[a] < rankv[b]) parent[a] = b;
        else if (rankv[b] < rankv[a]) parent[b] = a;
        else {
            parent[b] = a;
            rankv[a]++;
        }
    }

    int minConnect(int V, vector<vector<int>>& edges) {
        parent.resize(V);
        rankv.assign(V, 0);

        for (int i = 0; i < V; i++) parent[i] = i;

        int extra = 0;

        // Count components and extra edges
        for (auto &e : edges) {
            int u = e[0], v = e[1];
            if (findp(u) == findp(v))
                extra++;          // redundant edge
            else
                unite(u, v);
        }

        // Count number of connected components
        int components = 0;
        for (int i = 0; i < V; i++) {
            if (findp(i) == i)
                components++;
        }

        int needed = components - 1;
        if (extra >= needed) return needed;
        return -1;
    }
};

```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
