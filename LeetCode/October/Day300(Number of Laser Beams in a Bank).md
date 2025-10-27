--- ❤️ ---

# 🚀 _Day 300. Number of Laser Beams in a Bank_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/number-of-laser-beams-in-a-bank/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int numberOfBeams(vector<string>& bank) {
        int ans = 0, pre = 0;
        for (auto& row : bank) {
            int cur = count(row.begin(), row.end(), '1');
            if (cur) {
                ans += pre * cur;
                pre = cur;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int numberOfBeams(String[] bank) {
        int ans = 0, pre = 0;
        for (String row : bank) {
            int cur = 0;
            for (int i = 0; i < row.length(); ++i) {
                cur += row.charAt(i) - '0';
            }
            if (cur > 0) {
                ans += pre * cur;
                pre = cur;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def numberOfBeams(self, bank: List[str]) -> int:
        ans = pre = 0
        for row in bank:
            if (cur := row.count("1")) > 0:
                ans += pre * cur
                pre = cur
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
