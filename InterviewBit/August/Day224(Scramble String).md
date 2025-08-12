--- ❤️ ---

# 🚀 _Day 224. Scramble String_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/scramble-string/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <string>
#include <unordered_map>
#include <algorithm>

using namespace std;

class Solution {
public:
    bool isScramble(string A, string B) {
        unordered_map<string, bool> memo;
        return helper(A, B, memo);
    }
    
private:
    bool helper(string a, string b, unordered_map<string, bool>& memo) {
        string key = a + "#" + b;
        if (memo.find(key) != memo.end()) {
            return memo[key];
        }
        if (a.length() != b.length()) {
            memo[key] = false;
            return false;
        }
        if (a == b) {
            memo[key] = true;
            return true;
        }
        string sortedA = a;
        string sortedB = b;
        sort(sortedA.begin(), sortedA.end());
        sort(sortedB.begin(), sortedB.end());
        if (sortedA != sortedB) {
            memo[key] = false;
            return false;
        }
        int n = a.length();
        for (int i = 1; i < n; ++i) {
            if (helper(a.substr(0, i), b.substr(0, i), memo) && helper(a.substr(i), b.substr(i), memo)) {
                memo[key] = true;
                return true;
            }
            if (helper(a.substr(0, i), b.substr(n - i), memo) && helper(a.substr(i), b.substr(0, n - i), memo)) {
                memo[key] = true;
                return true;
            }
        }
        memo[key] = false;
        return false;
    }
};
```

## Code (Java)

```java
import java.util.HashMap;
import java.util.Arrays;

public class Solution {
    public int isScramble(String A, String B) {
        HashMap<String, Boolean> memo = new HashMap<>();
        return helper(A, B, memo) ? 1 : 0;
    }
    
    private boolean helper(String a, String b, HashMap<String, Boolean> memo) {
        String key = a + "#" + b;
        if (memo.containsKey(key)) {
            return memo.get(key);
        }
        if (a.length() != b.length()) {
            memo.put(key, false);
            return false;
        }
        if (a.equals(b)) {
            memo.put(key, true);
            return true;
        }
        char[] aChars = a.toCharArray();
        char[] bChars = b.toCharArray();
        Arrays.sort(aChars);
        Arrays.sort(bChars);
        if (!Arrays.equals(aChars, bChars)) {
            memo.put(key, false);
            return false;
        }
        int n = a.length();
        for (int i = 1; i < n; ++i) {
            if (helper(a.substring(0, i), b.substring(0, i), memo) && helper(a.substring(i), b.substring(i), memo)) {
                memo.put(key, true);
                return true;
            }
            if (helper(a.substring(0, i), b.substring(n - i), memo) && helper(a.substring(i), b.substring(0, n - i), memo)) {
                memo.put(key, true);
                return true;
            }
        }
        memo.put(key, false);
        return false;
    }
}
```

## Code (Python)

```python
class Solution:
    def isScramble(self, A, B):
        memo = {}
        
        def helper(a, b):
            if (a, b) in memo:
                return memo[(a, b)]
            if len(a) != len(b):
                memo[(a, b)] = False
                return False
            if a == b:
                memo[(a, b)] = True
                return True
            if sorted(a) != sorted(b):
                memo[(a, b)] = False
                return False
            n = len(a)
            for i in range(1, n):
                if (helper(a[:i], b[:i]) and helper(a[i:], b[i:])):
                    memo[(a, b)] = True
                    return True
                if (helper(a[:i], b[n-i:]) and helper(a[i:], b[:n-i])):
                    memo[(a, b)] = True
                    return True
            memo[(a, b)] = False
            return False
        
        return 1 if helper(A, B) else 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
