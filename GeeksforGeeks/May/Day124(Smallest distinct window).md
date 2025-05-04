# *124. Smallest Distinct Window*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/smallest-distant-window3132/1)


## **🧩 Problem Description**

Given a string `str`, find the length of the smallest window (substring) that contains **all the distinct characters** of the string **at least once**.


## Code(C++)
```cpp
class Solution {
  public:
    int findSubString(string& s) {
        unordered_set<char> all(s.begin(), s.end());
        int n = s.size(), i = 0, j = 0, d = all.size(), c = 0, res = n;
        vector<int> freq(256, 0);
        while (j < n) {
            if (++freq[s[j++]] == 1) c++;
            while (c == d) {
                res = min(res, j - i);
                if (--freq[s[i++]] == 0) c--;
            }
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int findSubString(String s) {
        Set<Character> all = new HashSet<>();
        for (char c : s.toCharArray()) all.add(c);
        int n = s.length(), i = 0, j = 0, d = all.size(), c = 0, res = n;
        int[] freq = new int[256];
        while (j < n) {
            if (++freq[s.charAt(j++)] == 1) c++;
            while (c == d) {
                res = Math.min(res, j - i);
                if (--freq[s.charAt(i++)] == 0) c--;
            }
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def findSubString(self, s):
        d = len(set(s))
        i = j = c = 0
        res = len(s)
        freq = [0]*256
        while j < len(s):
            if freq[ord(s[j])] == 0:
                c += 1
            freq[ord(s[j])] += 1
            j += 1
            while c == d:
                res = min(res, j - i)
                freq[ord(s[i])] -= 1
                if freq[ord(s[i])] == 0:
                    c -= 1
                i += 1
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
