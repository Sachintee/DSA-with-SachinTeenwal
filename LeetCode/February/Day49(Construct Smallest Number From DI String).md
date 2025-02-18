--- ❤️ ---

# 🚀 _Day 49. Construct Smallest Number From DI String_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/construct-smallest-number-from-di-string/description/?envType=daily-question&envId=2025-02-18)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    string ans = "";
    string pattern;
    vector<bool> vis;
    string t = "";

    string smallestNumber(string pattern) {
        this->pattern = pattern;
        vis.assign(10, false);
        dfs(0);
        return ans;
    }

    void dfs(int u) {
        if (ans != "") return;
        if (u == pattern.size() + 1) {
            ans = t;
            return;
        }
        for (int i = 1; i < 10; ++i) {
            if (!vis[i]) {
                if (u && pattern[u - 1] == 'I' && t.back() - '0' >= i) continue;
                if (u && pattern[u - 1] == 'D' && t.back() - '0' <= i) continue;
                vis[i] = true;
                t += to_string(i);
                dfs(u + 1);
                t.pop_back();
                vis[i] = false;
            }
        }
    }
};
```

## Code (Java)

```java
class Solution {
    private boolean[] vis = new boolean[10];
    private StringBuilder t = new StringBuilder();
    private String p;
    private String ans;

    public String smallestNumber(String pattern) {
        p = pattern;
        dfs(0);
        return ans;
    }

    private void dfs(int u) {
        if (ans != null) {
            return;
        }
        if (u == p.length() + 1) {
            ans = t.toString();
            return;
        }
        for (int i = 1; i < 10; ++i) {
            if (!vis[i]) {
                if (u > 0 && p.charAt(u - 1) == 'I' && t.charAt(u - 1) - '0' >= i) {
                    continue;
                }
                if (u > 0 && p.charAt(u - 1) == 'D' && t.charAt(u - 1) - '0' <= i) {
                    continue;
                }
                vis[i] = true;
                t.append(i);
                dfs(u + 1);
                t.deleteCharAt(t.length() - 1);
                vis[i] = false;
            }
        }
    }
}
```

## Code (Python)

```python
class Solution:
    def smallestNumber(self, pattern: str) -> str:
        def dfs(u):
            nonlocal ans
            if ans:
                return
            if u == len(pattern) + 1:
                ans = ''.join(t)
                return
            for i in range(1, 10):
                if not vis[i]:
                    if u and pattern[u - 1] == 'I' and int(t[-1]) >= i:
                        continue
                    if u and pattern[u - 1] == 'D' and int(t[-1]) <= i:
                        continue
                    vis[i] = True
                    t.append(str(i))
                    dfs(u + 1)
                    vis[i] = False
                    t.pop()

        vis = [False] * 10
        t = []
        ans = None
        dfs(0)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
