--- ❤️ ---

# 🚀 _Day 263. Implement Router_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/implement-router/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Router {
private:
    int lim;
    unordered_set<long long> vis;
    deque<array<int, 3>> q;
    unordered_map<int, int> idx;
    unordered_map<int, vector<int>> d;

    long long f(int a, int b, int c) {
        return ((long long) a << 46) | ((long long) b << 29) | (long long) c;
    }

public:
    Router(int memoryLimit) {
        lim = memoryLimit;
    }

    bool addPacket(int source, int destination, int timestamp) {
        long long x = f(source, destination, timestamp);
        if (vis.count(x)) {
            return false;
        }
        vis.insert(x);
        if ((int) q.size() >= lim) {
            forwardPacket();
        }
        q.push_back({source, destination, timestamp});
        d[destination].push_back(timestamp);
        return true;
    }

    vector<int> forwardPacket() {
        if (q.empty()) {
            return {};
        }
        auto packet = q.front();
        q.pop_front();
        int s = packet[0], d_ = packet[1], t = packet[2];
        vis.erase(f(s, d_, t));
        idx[d_]++;
        return {s, d_, t};
    }

    int getCount(int destination, int startTime, int endTime) {
        auto& ls = d[destination];
        int k = idx[destination];
        auto i = lower_bound(ls.begin() + k, ls.end(), startTime);
        auto j = lower_bound(ls.begin() + k, ls.end(), endTime + 1);
        return j - i;
    }
};

/**
 * Your Router object will be instantiated and called as such:
 * Router* obj = new Router(memoryLimit);
 * bool param_1 = obj->addPacket(source,destination,timestamp);
 * vector<int> param_2 = obj->forwardPacket();
 * int param_3 = obj->getCount(destination,startTime,endTime);
 */
```

## Code (Java)

```java
class Router {
    private int lim;
    private Set<Long> vis = new HashSet<>();
    private Deque<int[]> q = new ArrayDeque<>();
    private Map<Integer, Integer> idx = new HashMap<>();
    private Map<Integer, List<Integer>> d = new HashMap<>();

    public Router(int memoryLimit) {
        this.lim = memoryLimit;
    }

    public boolean addPacket(int source, int destination, int timestamp) {
        long x = f(source, destination, timestamp);
        if (vis.contains(x)) {
            return false;
        }
        vis.add(x);
        if (q.size() >= lim) {
            forwardPacket();
        }
        q.offer(new int[] {source, destination, timestamp});
        d.computeIfAbsent(destination, k -> new ArrayList<>()).add(timestamp);
        return true;
    }

    public int[] forwardPacket() {
        if (q.isEmpty()) {
            return new int[] {};
        }
        int[] packet = q.poll();
        int s = packet[0], d_ = packet[1], t = packet[2];
        vis.remove(f(s, d_, t));
        idx.merge(d_, 1, Integer::sum);
        return new int[] {s, d_, t};
    }

    private long f(int a, int b, int c) {
        return ((long) a << 46) | ((long) b << 29) | (long) c;
    }

    public int getCount(int destination, int startTime, int endTime) {
        List<Integer> ls = d.getOrDefault(destination, List.of());
        int k = idx.getOrDefault(destination, 0);
        int i = lowerBound(ls, startTime, k);
        int j = lowerBound(ls, endTime + 1, k);
        return j - i;
    }

    private int lowerBound(List<Integer> list, int target, int fromIndex) {
        int l = fromIndex, r = list.size();
        while (l < r) {
            int m = (l + r) >>> 1;
            if (list.get(m) < target) {
                l = m + 1;
            } else {
                r = m;
            }
        }
        return l;
    }
}

/**
 * Your Router object will be instantiated and called as such:
 * Router obj = new Router(memoryLimit);
 * boolean param_1 = obj.addPacket(source,destination,timestamp);
 * int[] param_2 = obj.forwardPacket();
 * int param_3 = obj.getCount(destination,startTime,endTime);
 */
```

## Code (Python)

```python
class Router:

    def __init__(self, memoryLimit: int):
        self.lim = memoryLimit
        self.vis = set()
        self.q = deque()
        self.idx = defaultdict(int)
        self.d = defaultdict(list)

    def addPacket(self, source: int, destination: int, timestamp: int) -> bool:
        x = self.f(source, destination, timestamp)
        if x in self.vis:
            return False
        self.vis.add(x)
        if len(self.q) >= self.lim:
            self.forwardPacket()
        self.q.append((source, destination, timestamp))
        self.d[destination].append(timestamp)
        return True

    def forwardPacket(self) -> List[int]:
        if not self.q:
            return []
        s, d, t = self.q.popleft()
        self.vis.remove(self.f(s, d, t))
        self.idx[d] += 1
        return [s, d, t]

    def f(self, a: int, b: int, c: int) -> int:
        return a << 46 | b << 29 | c

    def getCount(self, destination: int, startTime: int, endTime: int) -> int:
        ls = self.d[destination]
        k = self.idx[destination]
        i = bisect_left(ls, startTime, k)
        j = bisect_left(ls, endTime + 1, k)
        return j - i


# Your Router object will be instantiated and called as such:
# obj = Router(memoryLimit)
# param_1 = obj.addPacket(source,destination,timestamp)
# param_2 = obj.forwardPacket()
# param_3 = obj.getCount(destination,startTime,endTime)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
