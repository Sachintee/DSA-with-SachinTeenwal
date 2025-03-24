--- ❤️ ---

# 🚀 _Day 83. Count Days Without Meetings_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-days-without-meetings/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countDays(int days, vector<vector<int>>& meetings) {
        sort(meetings.begin(), meetings.end());
        int ans = 0, last = 0;
        for (auto& e : meetings) {
            int st = e[0], ed = e[1];
            if (last < st) {
                ans += st - last - 1;
            }
            last = max(last, ed);
        }
        ans += days - last;
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countDays(int days, int[][] meetings) {
        Arrays.sort(meetings, (a, b) -> a[0] - b[0]);
        int ans = 0, last = 0;
        for (var e : meetings) {
            int st = e[0], ed = e[1];
            if (last < st) {
                ans += st - last - 1;
            }
            last = Math.max(last, ed);
        }
        ans += days - last;
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def countDays(self, days: int, meetings: List[List[int]]) -> int:
        meetings.sort()
        ans = last = 0
        for st, ed in meetings:
            if last < st:
                ans += st - last - 1
            last = max(last, ed)
        ans += days - last
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
