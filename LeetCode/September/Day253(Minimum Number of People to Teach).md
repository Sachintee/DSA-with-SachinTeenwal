--- ❤️ ---

# 🚀 _Day 253. Minimum Number of People to Teach_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-number-of-people-to-teach/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minimumTeachings(int n, vector<vector<int>>& languages, vector<vector<int>>& friendships) {
        unordered_set<int> s;
        auto check = [&](int u, int v) {
            for (int x : languages[u - 1]) {
                for (int y : languages[v - 1]) {
                    if (x == y) {
                        return true;
                    }
                }
            }
            return false;
        };
        for (auto& e : friendships) {
            int u = e[0], v = e[1];
            if (!check(u, v)) {
                s.insert(u);
                s.insert(v);
            }
        }
        if (s.empty()) {
            return 0;
        }
        vector<int> cnt(n + 1);
        for (int u : s) {
            for (int& l : languages[u - 1]) {
                ++cnt[l];
            }
        }
        return s.size() - ranges::max(cnt);
    }
};
```

## Code (Java)

```java
class Solution {
    public int minimumTeachings(int n, int[][] languages, int[][] friendships) {
        Set<Integer> s = new HashSet<>();
        for (var e : friendships) {
            int u = e[0], v = e[1];
            if (!check(u, v, languages)) {
                s.add(u);
                s.add(v);
            }
        }
        if (s.isEmpty()) {
            return 0;
        }
        int[] cnt = new int[n + 1];
        for (int u : s) {
            for (int l : languages[u - 1]) {
                ++cnt[l];
            }
        }
        int mx = 0;
        for (int v : cnt) {
            mx = Math.max(mx, v);
        }
        return s.size() - mx;
    }

    private boolean check(int u, int v, int[][] languages) {
        for (int x : languages[u - 1]) {
            for (int y : languages[v - 1]) {
                if (x == y) {
                    return true;
                }
            }
        }
        return false;
    }
}
```

## Code (Python)

```python
class Solution:
    def minimumTeachings(
        self, n: int, languages: List[List[int]], friendships: List[List[int]]
    ) -> int:
        def check(u: int, v: int) -> bool:
            for x in languages[u - 1]:
                for y in languages[v - 1]:
                    if x == y:
                        return True
            return False

        s = set()
        for u, v in friendships:
            if not check(u, v):
                s.add(u)
                s.add(v)
        cnt = Counter()
        for u in s:
            for l in languages[u - 1]:
                cnt[l] += 1
        return len(s) - max(cnt.values(), default=0)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
