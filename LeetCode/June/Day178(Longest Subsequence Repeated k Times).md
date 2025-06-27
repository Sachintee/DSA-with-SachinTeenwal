--- ❤️ ---

# 🚀 _Day 178. Longest Subsequence Repeated k Times_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/longest-subsequence-repeated-k-times/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    string longestSubsequenceRepeatedK(string s, int k) {
        auto check = [&](const string& t, int k) -> bool {
            int i = 0;
            for (char c : s) {
                if (c == t[i]) {
                    i++;
                    if (i == t.size()) {
                        if (--k == 0) {
                            return true;
                        }
                        i = 0;
                    }
                }
            }
            return false;
        };
        int cnt[26] = {};
        for (char c : s) {
            cnt[c - 'a']++;
        }

        vector<char> cs;
        for (char c = 'a'; c <= 'z'; ++c) {
            if (cnt[c - 'a'] >= k) {
                cs.push_back(c);
            }
        }

        queue<string> q;
        q.push("");
        string ans;
        while (!q.empty()) {
            string cur = q.front();
            q.pop();
            for (char c : cs) {
                string nxt = cur + c;
                if (check(nxt, k)) {
                    ans = nxt;
                    q.push(nxt);
                }
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    private char[] s;

    public String longestSubsequenceRepeatedK(String s, int k) {
        this.s = s.toCharArray();
        int[] cnt = new int[26];
        for (char c : this.s) {
            cnt[c - 'a']++;
        }

        List<Character> cs = new ArrayList<>();
        for (char c = 'a'; c <= 'z'; ++c) {
            if (cnt[c - 'a'] >= k) {
                cs.add(c);
            }
        }
        Deque<String> q = new ArrayDeque<>();
        q.offer("");
        String ans = "";
        while (!q.isEmpty()) {
            String cur = q.poll();
            for (char c : cs) {
                String nxt = cur + c;
                if (check(nxt, k)) {
                    ans = nxt;
                    q.offer(nxt);
                }
            }
        }
        return ans;
    }

    private boolean check(String t, int k) {
        int i = 0;
        for (char c : s) {
            if (c == t.charAt(i)) {
                i++;
                if (i == t.length()) {
                    if (--k == 0) {
                        return true;
                    }
                    i = 0;
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
    def longestSubsequenceRepeatedK(self, s: str, k: int) -> str:
        def check(t: str, k: int) -> bool:
            i = 0
            for c in s:
                if c == t[i]:
                    i += 1
                    if i == len(t):
                        k -= 1
                        if k == 0:
                            return True
                        i = 0
            return False

        cnt = Counter(s)
        cs = [c for c in ascii_lowercase if cnt[c] >= k]
        q = deque([""])
        ans = ""
        while q:
            cur = q.popleft()
            for c in cs:
                nxt = cur + c
                if check(nxt, k):
                    ans = nxt
                    q.append(nxt)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
