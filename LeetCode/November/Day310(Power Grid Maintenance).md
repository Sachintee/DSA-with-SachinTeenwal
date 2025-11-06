--- ❤️ ---

# 🚀 _Day 310. Power Grid Maintenance_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/power-grid-maintenance/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class UnionFind {
public:
    UnionFind(int n) {
        p = vector<int>(n);
        size = vector<int>(n, 1);
        iota(p.begin(), p.end(), 0);
    }

    bool unite(int a, int b) {
        int pa = find(a), pb = find(b);
        if (pa == pb) {
            return false;
        }
        if (size[pa] > size[pb]) {
            p[pb] = pa;
            size[pa] += size[pb];
        } else {
            p[pa] = pb;
            size[pb] += size[pa];
        }
        return true;
    }

    int find(int x) {
        if (p[x] != x) {
            p[x] = find(p[x]);
        }
        return p[x];
    }

private:
    vector<int> p, size;
};

class Solution {
public:
    vector<int> processQueries(int c, vector<vector<int>>& connections, vector<vector<int>>& queries) {
        UnionFind uf(c + 1);
        for (auto& e : connections) {
            uf.unite(e[0], e[1]);
        }

        vector<set<int>> st(c + 1);
        for (int i = 1; i <= c; i++) {
            st[uf.find(i)].insert(i);
        }

        vector<int> ans;
        for (auto& q : queries) {
            int a = q[0], x = q[1];
            int root = uf.find(x);
            if (a == 1) {
                if (st[root].count(x)) {
                    ans.push_back(x);
                } else if (!st[root].empty()) {
                    ans.push_back(*st[root].begin());
                } else {
                    ans.push_back(-1);
                }
            } else {
                st[root].erase(x);
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class UnionFind {
    private final int[] p;
    private final int[] size;

    public UnionFind(int n) {
        p = new int[n];
        size = new int[n];
        for (int i = 0; i < n; ++i) {
            p[i] = i;
            size[i] = 1;
        }
    }

    public int find(int x) {
        if (p[x] != x) {
            p[x] = find(p[x]);
        }
        return p[x];
    }

    public boolean union(int a, int b) {
        int pa = find(a), pb = find(b);
        if (pa == pb) {
            return false;
        }
        if (size[pa] > size[pb]) {
            p[pb] = pa;
            size[pa] += size[pb];
        } else {
            p[pa] = pb;
            size[pb] += size[pa];
        }
        return true;
    }
}

class Solution {
    public int[] processQueries(int c, int[][] connections, int[][] queries) {
        UnionFind uf = new UnionFind(c + 1);
        for (int[] e : connections) {
            uf.union(e[0], e[1]);
        }

        TreeSet<Integer>[] st = new TreeSet[c + 1];
        Arrays.setAll(st, k -> new TreeSet<>());
        for (int i = 1; i <= c; i++) {
            int root = uf.find(i);
            st[root].add(i);
        }

        List<Integer> ans = new ArrayList<>();
        for (int[] q : queries) {
            int a = q[0], x = q[1];
            int root = uf.find(x);

            if (a == 1) {
                if (st[root].contains(x)) {
                    ans.add(x);
                } else if (!st[root].isEmpty()) {
                    ans.add(st[root].first());
                } else {
                    ans.add(-1);
                }
            } else {
                st[root].remove(x);
            }
        }

        return ans.stream().mapToInt(Integer::intValue).toArray();
    }
}
```

## Code (Python)

```python
class UnionFind:
    def __init__(self, n):
        self.p = list(range(n))
        self.size = [1] * n

    def find(self, x):
        if self.p[x] != x:
            self.p[x] = self.find(self.p[x])
        return self.p[x]

    def union(self, a, b):
        pa, pb = self.find(a), self.find(b)
        if pa == pb:
            return False
        if self.size[pa] > self.size[pb]:
            self.p[pb] = pa
            self.size[pa] += self.size[pb]
        else:
            self.p[pa] = pb
            self.size[pb] += self.size[pa]
        return True


class Solution:
    def processQueries(
        self, c: int, connections: List[List[int]], queries: List[List[int]]
    ) -> List[int]:
        uf = UnionFind(c + 1)
        for u, v in connections:
            uf.union(u, v)
        st = [SortedList() for _ in range(c + 1)]
        for i in range(1, c + 1):
            st[uf.find(i)].add(i)
        ans = []
        for a, x in queries:
            root = uf.find(x)
            if a == 1:
                if x in st[root]:
                    ans.append(x)
                elif len(st[root]):
                    ans.append(st[root][0])
                else:
                    ans.append(-1)
            else:
                st[root].discard(x)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
