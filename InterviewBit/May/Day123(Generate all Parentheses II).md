--- ❤️ ---

# 🚀 _Day 123. Generate all Parentheses II_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/generate-all-parentheses-ii/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>

using namespace std;

class Solution {
public:
    vector<string> generateParenthesis(int n) {
        vector<string> result;
        backtrack(n, 0, 0, "", result);
        return result;
    }
    
private:
    void backtrack(int n, int open, int close, string current, vector<string>& result) {
        if (current.length() == 2 * n) {
            result.push_back(current);
            return;
        }
        if (open < n) {
            backtrack(n, open + 1, close, current + "(", result);
        }
        if (close < open) {
            backtrack(n, open, close + 1, current + ")", result);
        }
    }
};
```

## Code (Java)

```java
import java.util.ArrayList;
import java.util.List;

class Solution {
    public List<String> generateParenthesis(int n) {
        List<String> result = new ArrayList<>();
        backtrack(n, 0, 0, new StringBuilder(), result);
        return result;
    }
    
    private void backtrack(int n, int open, int close, StringBuilder current, List<String> result) {
        if (current.length() == 2 * n) {
            result.add(current.toString());
            return;
        }
        if (open < n) {
            current.append("(");
            backtrack(n, open + 1, close, current, result);
            current.deleteCharAt(current.length() - 1);
        }
        if (close < open) {
            current.append(")");
            backtrack(n, open, close + 1, current, result);
            current.deleteCharAt(current.length() - 1);
        }
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : integer
    # @return a list of strings
    def generateParenthesis(self, A):
        result = []
        self.backtrack(A, 0, 0, "", result)
        return result
    
    def backtrack(self, A, open_count, close_count, current, result):
        if len(current) == 2 * A:
            result.append(current)
            return
        if open_count < A:
            self.backtrack(A, open_count + 1, close_count, current + "(", result)
        if close_count < open_count:
            self.backtrack(A, open_count, close_count + 1, current + ")", result)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
