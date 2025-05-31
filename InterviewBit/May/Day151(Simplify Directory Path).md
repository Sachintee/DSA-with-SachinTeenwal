--- ❤️ ---

# 🚀 _Day 151. Simplify Directory Path_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/simplify-directory-path/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>
#include <sstream>

using namespace std;

class Solution {
public:
    string simplifyPath(string A) {
        vector<string> stack;
        stringstream ss(A);
        string part;
        
        while (getline(ss, part, '/')) {
            if (part.empty() || part == ".") {
                continue;
            } else if (part == "..") {
                if (!stack.empty()) {
                    stack.pop_back();
                }
            } else {
                stack.push_back(part);
            }
        }
        
        string simplifiedPath;
        for (const string& dir : stack) {
            simplifiedPath += "/" + dir;
        }
        
        return simplifiedPath.empty() ? "/" : simplifiedPath;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public String simplifyPath(String A) {
        String[] parts = A.split("/");
        Deque<String> stack = new ArrayDeque<>();
        
        for (String part : parts) {
            if (part.isEmpty() || part.equals(".")) {
                continue;
            } else if (part.equals("..")) {
                if (!stack.isEmpty()) {
                    stack.pop();
                }
            } else {
                stack.push(part);
            }
        }
        
        StringBuilder simplifiedPath = new StringBuilder();
        for (String dir : stack) {
            simplifiedPath.insert(0, "/" + dir);
        }
        
        return simplifiedPath.length() == 0 ? "/" : simplifiedPath.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : string
    # @return a strings
    def simplifyPath(self, A):
        components = A.split('/')
        stack = []
        for part in components:
            if part == '' or part == '.':
                continue
            elif part == '..':
                if stack:
                    stack.pop()
            else:
                stack.append(part)
        simplified_path = '/' + '/'.join(stack)
        return simplified_path
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
