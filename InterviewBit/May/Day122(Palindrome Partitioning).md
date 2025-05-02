--- ❤️ ---

# 🚀 _Day 122. Palindrome Partitioning_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/palindrome-partitioning/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>
#include <algorithm>

using namespace std;

class Solution {
public:
    vector<vector<string>> partition(string s) {
        vector<vector<string>> result;
        vector<string> path;
        backtrack(s, 0, path, result);
        return result;
    }
    
private:
    void backtrack(const string& s, int start, vector<string>& path, vector<vector<string>>& result) {
        if (start == s.length()) {
            result.push_back(path);
            return;
        }
        for (int end = start + 1; end <= s.length(); ++end) {
            string substring = s.substr(start, end - start);
            if (isPalindrome(substring)) {
                path.push_back(substring);
                backtrack(s, end, path, result);
                path.pop_back();
            }
        }
    }
    
    bool isPalindrome(const string& s) {
        int left = 0;
        int right = s.length() - 1;
        while (left < right) {
            if (s[left] != s[right]) {
                return false;
            }
            left++;
            right--;
        }
        return true;
    }
};
```

## Code (Java)

```java
import java.util.ArrayList;
import java.util.List;

class Solution {
    public List<List<String>> partition(String s) {
        List<List<String>> result = new ArrayList<>();
        backtrack(s, 0, new ArrayList<>(), result);
        return result;
    }
    
    private void backtrack(String s, int start, List<String> path, List<List<String>> result) {
        if (start == s.length()) {
            result.add(new ArrayList<>(path));
            return;
        }
        for (int end = start + 1; end <= s.length(); end++) {
            String substring = s.substring(start, end);
            if (isPalindrome(substring)) {
                path.add(substring);
                backtrack(s, end, path, result);
                path.remove(path.size() - 1);
            }
        }
    }
    
    private boolean isPalindrome(String s) {
        int left = 0;
        int right = s.length() - 1;
        while (left < right) {
            if (s.charAt(left) != s.charAt(right)) {
                return false;
            }
            left++;
            right--;
        }
        return true;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : string
    # @return a list of list of strings
    def partition(self, A):
        result = []
        self.backtrack(A, [], result)
        return result
    
    def backtrack(self, s, path, result):
        if not s:
            result.append(list(path))
            return
        for i in range(1, len(s) + 1):
            substring = s[:i]
            if self.is_palindrome(substring):
                path.append(substring)
                self.backtrack(s[i:], path, result)
                path.pop()
    
    def is_palindrome(self, s):
        return s == s[::-1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
