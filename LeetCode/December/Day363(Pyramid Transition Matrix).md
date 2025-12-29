

# 🚀 _Day 363. Pyramid Transition Matrix_ 


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/pyramid-transition-matrix/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int d[7][7];
    unordered_map<string, bool> f;

    bool pyramidTransition(string bottom, vector<string>& allowed) {
        memset(d, 0, sizeof(d));
        for (auto& s : allowed) {
            int a = s[0] - 'A', b = s[1] - 'A';
            d[a][b] |= 1 << (s[2] - 'A');
        }
        return dfs(bottom, "");
    }

    bool dfs(string& s, string t) {
        if (s.size() == 1) {
            return true;
        }
        if (t.size() + 1 == s.size()) {
            return dfs(t, "");
        }
        string k = s + "." + t;
        if (f.contains(k)) {
            return f[k];
        }
        int a = s[t.size()] - 'A', b = s[t.size() + 1] - 'A';
        int cs = d[a][b];
        for (int i = 0; i < 7; ++i) {
            if (cs >> i & 1) {
                if (dfs(s, t + (char) (i + 'A'))) {
                    f[k] = true;
                    return true;
                }
            }
        }
        f[k] = false;
        return false;
    }
};
```

## Code (Java)

```java
class Solution {
    private final int[][] d = new int[7][7];
    private final Map<String, Boolean> f = new HashMap<>();

    public boolean pyramidTransition(String bottom, List<String> allowed) {
        for (String s : allowed) {
            int a = s.charAt(0) - 'A', b = s.charAt(1) - 'A';
            d[a][b] |= 1 << (s.charAt(2) - 'A');
        }
        return dfs(bottom, new StringBuilder());
    }

    private boolean dfs(String s, StringBuilder t) {
        if (s.length() == 1) {
            return true;
        }
        if (t.length() + 1 == s.length()) {
            return dfs(t.toString(), new StringBuilder());
        }
        String k = s + "." + t.toString();
        Boolean res = f.get(k);
        if (res != null) {
            return res;
        }
        int a = s.charAt(t.length()) - 'A', b = s.charAt(t.length() + 1) - 'A';
        int cs = d[a][b];
        for (int i = 0; i < 7; ++i) {
            if (((cs >> i) & 1) == 1) {
                t.append((char) ('A' + i));
                if (dfs(s, t)) {
                    f.put(k, true);
                    return true;
                }
                t.setLength(t.length() - 1);
            }
        }
        f.put(k, false);
        return false;
    }
}
```

## Code (Python)

```python
class Solution:
    def pyramidTransition(self, bottom: str, allowed: List[str]) -> bool:
        @cache
        def dfs(s: str) -> bool:
            if len(s) == 1:
                return True
            t = []
            for a, b in pairwise(s):
                cs = d[a, b]
                if not cs:
                    return False
                t.append(cs)
            return any(dfs("".join(nxt)) for nxt in product(*t))

        d = defaultdict(list)
        for a, b, c in allowed:
            d[a, b].append(c)
        return dfs(bottom)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
