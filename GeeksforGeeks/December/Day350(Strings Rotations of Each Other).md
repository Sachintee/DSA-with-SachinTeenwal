--- ❤️ ---

# 🚀 _Day 350. Strings Rotations of Each Other_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/check-if-strings-are-rotations-of-each-other-or-not-1587115620/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    bool areRotations(string &s1, string &s2) {
        if (s1.length() != s2.length())
            return false;

        string temp = s1 + s1;
        return temp.find(s2) != string::npos;
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
