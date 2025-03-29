--- ❤️ ---

# 🚀 _Day 88. Longest Palindromic Substring_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/longest-palindromic-substring/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <string>
#include <algorithm>

using namespace std;

class Solution {
public:
    string longestPalindrome(string A) {
        if (A.empty()) return "";
        
        int start = 0;
        int end = 0;
        
        for (int i = 0; i < A.size(); ++i) {
            int len1 = expandAroundCenter(A, i, i);
            int len2 = expandAroundCenter(A, i, i + 1);
            int max_len = max(len1, len2);
            if (max_len > end - start + 1 || (max_len == end - start + 1 && i - (max_len - 1) / 2 < start)) {
                start = i - (max_len - 1) / 2;
                end = i + max_len / 2;
            }
        }
        
        return A.substr(start, end - start + 1);
    }
    
private:
    int expandAroundCenter(const string& s, int left, int right) {
        while (left >= 0 && right < s.size() && s[left] == s[right]) {
            --left;
            ++right;
        }
        return right - left - 1;
    }
};
```

## Code (Java)

```java
class Solution {
    public String longestPalindrome(String A) {
        if (A == null || A.isEmpty()) return "";
        
        int start = 0;
        int end = 0;
        
        for (int i = 0; i < A.length(); i++) {
            int len1 = expandAroundCenter(A, i, i);
            int len2 = expandAroundCenter(A, i, i + 1);
            int maxLen = Math.max(len1, len2);
            if (maxLen > end - start + 1 || (maxLen == end - start + 1 && i - (maxLen - 1) / 2 < start)) {
                start = i - (maxLen - 1) / 2;
                end = i + maxLen / 2;
            }
        }
        
        return A.substring(start, end + 1);
    }
    
    private int expandAroundCenter(String s, int left, int right) {
        while (left >= 0 && right < s.length() && s.charAt(left) == s.charAt(right)) {
            left--;
            right++;
        }
        return right - left - 1;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestPalindrome(self, A):
        if not A:
            return ""
        
        start = 0
        end = 0
        
        for i in range(len(A)):
            len1 = self.expandAroundCenter(A, i, i)
            len2 = self.expandAroundCenter(A, i, i + 1)
            max_len = max(len1, len2)
            if max_len > end - start + 1 or (max_len == end - start + 1 and i - (max_len - 1) // 2 < start):
                start = i - (max_len - 1) // 2
                end = i + max_len // 2
        
        return A[start:end + 1]
    
    def expandAroundCenter(self, s, left, right):
        while left >= 0 and right < len(s) and s[left] == s[right]:
            left -= 1
            right += 1
        return right - left - 1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
