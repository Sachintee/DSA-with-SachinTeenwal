--- ❤️ ---

# 🚀 _Day 344. String Inversion_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/string-inversion/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    string solve(string A) {
        for (char &c : A) {
            if (islower(c)) 
                c = toupper(c);
            else 
                c = tolower(c);
        }
        return A;
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
