--- ❤️ ---

# 🚀 _Day 157. Using a Robot to Print the Lexicographically Smallest String_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/using-a-robot-to-print-the-lexicographically-smallest-string/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    string robotWithString(string s) {
        int cnt[26] = {0};
        for (char& c : s) ++cnt[c - 'a'];
        char mi = 'a';
        string stk;
        string ans;
        for (char& c : s) {
            --cnt[c - 'a'];
            while (mi < 'z' && cnt[mi - 'a'] == 0) ++mi;
            stk += c;
            while (!stk.empty() && stk.back() <= mi) {
                ans += stk.back();
                stk.pop_back();
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public String robotWithString(String s) {
        int[] cnt = new int[26];
        for (char c : s.toCharArray()) {
            ++cnt[c - 'a'];
        }
        StringBuilder ans = new StringBuilder();
        Deque<Character> stk = new ArrayDeque<>();
        char mi = 'a';
        for (char c : s.toCharArray()) {
            --cnt[c - 'a'];
            while (mi < 'z' && cnt[mi - 'a'] == 0) {
                ++mi;
            }
            stk.push(c);
            while (!stk.isEmpty() && stk.peek() <= mi) {
                ans.append(stk.pop());
            }
        }
        return ans.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def robotWithString(self, s: str) -> str:
        cnt = Counter(s)
        ans = []
        stk = []
        mi = 'a'
        for c in s:
            cnt[c] -= 1
            while mi < 'z' and cnt[mi] == 0:
                mi = chr(ord(mi) + 1)
            stk.append(c)
            while stk and stk[-1] <= mi:
                ans.append(stk.pop())
        return ''.join(ans)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
