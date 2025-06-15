--- ❤️ ---

# 🚀 _Day 166. Max Difference You Can Get From Changing an Integer_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/max-difference-you-can-get-from-changing-an-integer/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maxDiff(int num) {
        auto replace = [](string& s, char a, char b) {
            for (auto& c : s) {
                if (c == a) {
                    c = b;
                }
            }
        };
        string a = to_string(num);
        string b = a;
        for (int i = 0; i < a.size(); ++i) {
            if (a[i] != '9') {
                replace(a, a[i], '9');
                break;
            }
        }
        if (b[0] != '1') {
            replace(b, b[0], '1');
        } else {
            for (int i = 1; i < b.size(); ++i) {
                if (b[i] != '0' && b[i] != '1') {
                    replace(b, b[i], '0');
                    break;
                }
            }
        }
        return stoi(a) - stoi(b);
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxDiff(int num) {
        String a = String.valueOf(num);
        String b = a;
        for (int i = 0; i < a.length(); ++i) {
            if (a.charAt(i) != '9') {
                a = a.replace(a.charAt(i), '9');
                break;
            }
        }
        if (b.charAt(0) != '1') {
            b = b.replace(b.charAt(0), '1');
        } else {
            for (int i = 1; i < b.length(); ++i) {
                if (b.charAt(i) != '0' && b.charAt(i) != '1') {
                    b = b.replace(b.charAt(i), '0');
                    break;
                }
            }
        }
        return Integer.parseInt(a) - Integer.parseInt(b);
    }
}
```

## Code (Python)

```python
class Solution:
    def maxDiff(self, num: int) -> int:
        a, b = str(num), str(num)
        for c in a:
            if c != "9":
                a = a.replace(c, "9")
                break
        if b[0] != "1":
            b = b.replace(b[0], "1")
        else:
            for c in b[1:]:
                if c not in "01":
                    b = b.replace(c, "0")
                    break
        return int(a) - int(b)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
