--- ❤️ ---

# 🚀 _Day 286. Find Resultant Array After Removing Anagrams_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-resultant-array-after-removing-anagrams/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<string> removeAnagrams(vector<string>& words) {
        auto check = [](string& s, string& t) -> bool {
            if (s.size() != t.size()) {
                return true;
            }
            int cnt[26]{};
            for (char& c : s) {
                ++cnt[c - 'a'];
            }
            for (char& c : t) {
                if (--cnt[c - 'a'] < 0) {
                    return true;
                }
            }
            return false;
        };

        vector<string> ans = {words[0]};
        for (int i = 1; i < words.size(); ++i) {
            if (check(words[i - 1], words[i])) {
                ans.emplace_back(words[i]);
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public List<String> removeAnagrams(String[] words) {
        List<String> ans = new ArrayList<>();
        ans.add(words[0]);
        for (int i = 1; i < words.length; ++i) {
            if (check(words[i - 1], words[i])) {
                ans.add(words[i]);
            }
        }
        return ans;
    }

    private boolean check(String s, String t) {
        if (s.length() != t.length()) {
            return true;
        }
        int[] cnt = new int[26];
        for (int i = 0; i < s.length(); ++i) {
            ++cnt[s.charAt(i) - 'a'];
        }
        for (int i = 0; i < t.length(); ++i) {
            if (--cnt[t.charAt(i) - 'a'] < 0) {
                return true;
            }
        }
        return false;
    }
}
```

## Code (Python)

```python
class Solution:
    def removeAnagrams(self, words: List[str]) -> List[str]:
        def check(s: str, t: str) -> bool:
            if len(s) != len(t):
                return True
            cnt = Counter(s)
            for c in t:
                cnt[c] -= 1
                if cnt[c] < 0:
                    return True
            return False

        return [words[0]] + [t for s, t in pairwise(words) if check(s, t)]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
