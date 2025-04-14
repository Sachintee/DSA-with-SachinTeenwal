---
Difficulty: Hard
Source: 160 Days of Problem Solving
Tags:
  - Graph
  - Strings
  - Sorting
---

# 🚀 _Day 104. Alien Dictionary_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/alien-dictionary)  



## 💡 **Problem Description:**

A new alien language uses the English alphabet, but the order of the letters is unknown. You are given a list of words from the alien language’s dictionary, where the words are said to be sorted lexicographically by the language's own letter order.

Your task is to **determine the correct order of letters** based on the given words.  
If multiple valid orderings are possible, return any one of them.  
If no valid ordering exists (i.e., the words are not consistent with any letter ordering), return an empty string (`""`).


## Code(C++)
```cpp
class Solution {
  public:
    string findOrder(vector<string> &w) {
        vector<vector<int>> g(26);
        vector<int> in(26), seen(26);
        for (auto &s : w) for (char c : s) seen[c - 'a'] = 1;
        for (int i = 0; i < w.size() - 1; i++) {
            string &a = w[i], &b = w[i + 1];
            int j = 0, n = min(a.size(), b.size());
            while (j < n && a[j] == b[j]) j++;
            if (j == n && a.size() > b.size()) return "";
            if (j < n) g[a[j] - 'a'].push_back(b[j] - 'a'), in[b[j] - 'a']++;
        }
        queue<int> q;
        for (int i = 0; i < 26; i++) if (seen[i] && !in[i]) q.push(i);
        string res;
        while (!q.empty()) {
            int u = q.front(); q.pop();
            res += u + 'a';
            for (int v : g[u]) if (--in[v] == 0) q.push(v);
        }
        for (int i = 0; i < 26; i++) if (seen[i] && in[i]) return "";
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public String findOrder(String[] w) {
        List<List<Integer>> g = new ArrayList<>();
        int[] in = new int[26];
        boolean[] seen = new boolean[26];
        for (int i = 0; i < 26; i++) g.add(new ArrayList<>());
        for (String s : w) for (char c : s.toCharArray()) seen[c - 'a'] = true;
        for (int i = 0; i < w.length - 1; i++) {
            String a = w[i], b = w[i + 1];
            int j = 0, n = Math.min(a.length(), b.length());
            while (j < n && a.charAt(j) == b.charAt(j)) j++;
            if (j == n && a.length() > b.length()) return "";
            if (j < n) {
                g.get(a.charAt(j) - 'a').add(b.charAt(j) - 'a');
                in[b.charAt(j) - 'a']++;
            }
        }
        Queue<Integer> q = new LinkedList<>();
        for (int i = 0; i < 26; i++) if (seen[i] && in[i] == 0) q.add(i);
        StringBuilder res = new StringBuilder();
        while (!q.isEmpty()) {
            int u = q.poll();
            res.append((char)(u + 'a'));
            for (int v : g.get(u)) if (--in[v] == 0) q.add(v);
        }
        for (int i = 0; i < 26; i++) if (seen[i] && in[i] > 0) return "";
        return res.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    @staticmethod
    def findOrder(words):
        from collections import deque, defaultdict
        g = defaultdict(list)
        in_deg = [0] * 26
        seen = [0] * 26
        for w in words:
            for c in w:
                seen[ord(c) - 97] = 1
        for i in range(len(words) - 1):
            a, b = words[i], words[i + 1]
            j, n = 0, min(len(a), len(b))
            while j < n and a[j] == b[j]: j += 1
            if j == n and len(a) > len(b): return ""
            if j < n:
                u, v = ord(a[j]) - 97, ord(b[j]) - 97
                g[u].append(v)
                in_deg[v] += 1
        q = deque(i for i in range(26) if seen[i] and in_deg[i] == 0)
        res = []
        while q:
            u = q.popleft()
            res.append(chr(u + 97))
            for v in g[u]:
                in_deg[v] -= 1
                if in_deg[v] == 0: q.append(v)
        return "".join(res) if sum(seen) == len(res) else ""
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
