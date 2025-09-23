--- ❤️ ---

# 🚀 _Day 266. Compare Version Numbers_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/compare-version-numbers/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int compareVersion(string version1, string version2) {
        int m = version1.size(), n = version2.size();
        for (int i = 0, j = 0; i < m || j < n; ++i, ++j) {
            int a = 0, b = 0;
            while (i < m && version1[i] != '.') {
                a = a * 10 + (version1[i++] - '0');
            }
            while (j < n && version2[j] != '.') {
                b = b * 10 + (version2[j++] - '0');
            }
            if (a != b) {
                return a < b ? -1 : 1;
            }
        }
        return 0;
    }
};
```

## Code (Java)

```java
class Solution {
    public int compareVersion(String version1, String version2) {
        int m = version1.length(), n = version2.length();
        for (int i = 0, j = 0; i < m || j < n; ++i, ++j) {
            int a = 0, b = 0;
            while (i < m && version1.charAt(i) != '.') {
                a = a * 10 + (version1.charAt(i++) - '0');
            }
            while (j < n && version2.charAt(j) != '.') {
                b = b * 10 + (version2.charAt(j++) - '0');
            }
            if (a != b) {
                return a < b ? -1 : 1;
            }
        }
        return 0;
    }
}
```

## Code (Python)

```python
class Solution:
    def compareVersion(self, version1: str, version2: str) -> int:
        m, n = len(version1), len(version2)
        i = j = 0
        while i < m or j < n:
            a = b = 0
            while i < m and version1[i] != '.':
                a = a * 10 + int(version1[i])
                i += 1
            while j < n and version2[j] != '.':
                b = b * 10 + int(version2[j])
                j += 1
            if a != b:
                return -1 if a < b else 1
            i, j = i + 1, j + 1
        return 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
