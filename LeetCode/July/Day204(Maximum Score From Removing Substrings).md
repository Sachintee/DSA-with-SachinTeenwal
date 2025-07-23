--- ❤️ ---

# 🚀 _Day204 Maximum Score From Removing Substrings. _ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-score-from-removing-substrings/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maximumGain(string s, int x, int y) {
        char a = 'a', b = 'b';
        if (x < y) {
            swap(x, y);
            swap(a, b);
        }

        int ans = 0, cnt1 = 0, cnt2 = 0;
        for (char c : s) {
            if (c == a) {
                cnt1++;
            } else if (c == b) {
                if (cnt1) {
                    ans += x;
                    cnt1--;
                } else {
                    cnt2++;
                }
            } else {
                ans += min(cnt1, cnt2) * y;
                cnt1 = 0;
                cnt2 = 0;
            }
        }
        ans += min(cnt1, cnt2) * y;
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maximumGain(String s, int x, int y) {
        char a = 'a', b = 'b';
        if (x < y) {
            int t = x;
            x = y;
            y = t;
            char c = a;
            a = b;
            b = c;
        }
        int ans = 0, cnt1 = 0, cnt2 = 0;
        int n = s.length();
        for (int i = 0; i < n; ++i) {
            char c = s.charAt(i);
            if (c == a) {
                cnt1++;
            } else if (c == b) {
                if (cnt1 > 0) {
                    ans += x;
                    cnt1--;
                } else {
                    cnt2++;
                }
            } else {
                ans += Math.min(cnt1, cnt2) * y;
                cnt1 = 0;
                cnt2 = 0;
            }
        }
        ans += Math.min(cnt1, cnt2) * y;
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maximumGain(self, s: str, x: int, y: int) -> int:
        a, b = "a", "b"
        if x < y:
            x, y = y, x
            a, b = b, a
        ans = cnt1 = cnt2 = 0
        for c in s:
            if c == a:
                cnt1 += 1
            elif c == b:
                if cnt1:
                    ans += x
                    cnt1 -= 1
                else:
                    cnt2 += 1
            else:
                ans += min(cnt1, cnt2) * y
                cnt1 = cnt2 = 0
        ans += min(cnt1, cnt2) * y
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
