--- ❤️ ---

# 🚀 _Day 50. The k-th Lexicographical String of All Happy Strings of Length n_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/the-k-th-lexicographical-string-of-all-happy-strings-of-length-n/description/?envType=daily-question&envId=2025-02-19)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<string> ans;
    string getHappyString(int n, int k) {
        dfs("", n);
        return ans.size() < k ? "" : ans[k - 1];
    }

    void dfs(string t, int n) {
        if (t.size() == n) {
            ans.push_back(t);
            return;
        }
        for (int c = 'a'; c <= 'c'; ++c) {
            if (t.size() && t.back() == c) continue;
            t.push_back(c);
            dfs(t, n);
            t.pop_back();
        }
    }
};
```

## Code (Java)

```java
class Solution {
    private List<String> ans = new ArrayList<>();

    public String getHappyString(int n, int k) {
        dfs("", n);
        return ans.size() < k ? "" : ans.get(k - 1);
    }

    private void dfs(String t, int n) {
        if (t.length() == n) {
            ans.add(t);
            return;
        }
        for (char c : "abc".toCharArray()) {
            if (t.length() > 0 && t.charAt(t.length() - 1) == c) {
                continue;
            }
            dfs(t + c, n);
        }
    }
}
```

## Code (Python)

```python
class Solution:
    def getHappyString(self, n: int, k: int) -> str:
        def dfs(t):
            if len(t) == n:
                ans.append(t)
                return
            for c in 'abc':
                if t and t[-1] == c:
                    continue
                dfs(t + c)

        ans = []
        dfs('')
        return '' if len(ans) < k else ans[k - 1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
