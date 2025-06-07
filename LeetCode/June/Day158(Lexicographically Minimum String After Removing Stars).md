--- ❤️ ---

# 🚀 _Day 158. Lexicographically Minimum String After Removing Stars_ 🧠


The problem can be found at the following link: [Problem Link](Lexicographically Minimum String After Removing Stars)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    string clearStars(string s) {
        stack<int> g[26];
        int n = s.length();
        vector<bool> rem(n);
        for (int i = 0; i < n; ++i) {
            if (s[i] == '*') {
                rem[i] = true;
                for (int j = 0; j < 26; ++j) {
                    if (!g[j].empty()) {
                        rem[g[j].top()] = true;
                        g[j].pop();
                        break;
                    }
                }
            } else {
                g[s[i] - 'a'].push(i);
            }
        }
        string ans;
        for (int i = 0; i < n; ++i) {
            if (!rem[i]) {
                ans.push_back(s[i]);
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public String clearStars(String s) {
        Deque<Integer>[] g = new Deque[26];
        Arrays.setAll(g, k -> new ArrayDeque<>());
        int n = s.length();
        boolean[] rem = new boolean[n];
        for (int i = 0; i < n; ++i) {
            if (s.charAt(i) == '*') {
                rem[i] = true;
                for (int j = 0; j < 26; ++j) {
                    if (!g[j].isEmpty()) {
                        rem[g[j].pop()] = true;
                        break;
                    }
                }
            } else {
                g[s.charAt(i) - 'a'].push(i);
            }
        }
        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < n; ++i) {
            if (!rem[i]) {
                sb.append(s.charAt(i));
            }
        }
        return sb.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def clearStars(self, s: str) -> str:
        g = defaultdict(list)
        n = len(s)
        rem = [False] * n
        for i, c in enumerate(s):
            if c == "*":
                rem[i] = True
                for a in ascii_lowercase:
                    if g[a]:
                        rem[g[a].pop()] = True
                        break
            else:
                g[c].append(i)
        return "".join(c for i, c in enumerate(s) if not rem[i])
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
