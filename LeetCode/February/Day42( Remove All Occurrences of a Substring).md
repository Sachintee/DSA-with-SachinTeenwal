--- ❤️ ---

# 🚀 _Day 42.  Remove All Occurrences of a Substring_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/remove-all-occurrences-of-a-substring/submissions/1539340380/?envType=daily-question&envId=2025-02-11)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    string removeOccurrences(string s, string part) {
        int m = part.size();
        while (s.find(part) != -1) {
            s = s.erase(s.find(part), m);
        }
        return s;
    }
};
```

## Code (Java)

```java
class Solution {
    public String removeOccurrences(String s, String part) {
        while (s.contains(part)) {
            s = s.replaceFirst(part, "");
        }
        return s;
    }
}
```

## Code (Python)

```python
class Solution:
    def removeOccurrences(self, s: str, part: str) -> str:
        while part in s:
            s = s.replace(part, '', 1)
        return s
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
