--- ❤️ ---

# 🚀 _Day 155. Find the Lexicographically Largest String From the Box I_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-the-lexicographically-largest-string-from-the-box-i/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    string answerString(string word, int numFriends) {
        if (numFriends == 1) {
            return word;
        }
        int n = word.length();
        string ans = "";
        for (int i = 0; i < n; ++i) {
            string t = word.substr(i, min(n - i, n - (numFriends - 1)));
            if (ans < t) {
                ans = t;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public String answerString(String word, int numFriends) {
        if (numFriends == 1) {
            return word;
        }
        int n = word.length();
        String ans = "";
        for (int i = 0; i < n; ++i) {
            String t = word.substring(i, Math.min(n, i + n - (numFriends - 1)));
            if (ans.compareTo(t) < 0) {
                ans = t;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def answerString(self, word: str, numFriends: int) -> str:
        if numFriends == 1:
            return word
        n = len(word)
        return max(word[i : i + n - (numFriends - 1)] for i in range(n))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
