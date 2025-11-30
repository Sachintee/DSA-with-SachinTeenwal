--- ❤️ ---

# 🚀 _Day 334. Count of distinct substrings_ 🧠


The problem can be found at the following link: [Problem Link]()

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countSubs(string& s) {
        int cnt = 0, n = s.length();
        struct Node { Node* c[26] = {}; };
        Node* root = new Node();
        for (int i = 0; i < n; i++) {
            Node* cur = root;
            for (int j = i; j < n; j++) {
                int idx = s[j] - 'a';
                if (!cur->c[idx]) {
                    cur->c[idx] = new Node();
                    cnt++;
                }
                cur = cur->c[idx];
            }
        }
        return cnt;
    }
};
```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
