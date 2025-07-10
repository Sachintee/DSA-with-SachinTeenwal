--- ❤️ ---

# 🚀 _Day 191. Reschedule Meetings for Maximum Free Time II_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/reschedule-meetings-for-maximum-free-time-ii/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maxFreeTime(int eventTime, vector<int>& startTime, vector<int>& endTime) {
        int n = startTime.size();
        vector<int> pre(n), suf(n);

        pre[0] = startTime[0];
        suf[n - 1] = eventTime - endTime[n - 1];

        for (int i = 1; i < n; ++i) {
            pre[i] = max(pre[i - 1], startTime[i] - endTime[i - 1]);
        }

        for (int i = n - 2; i >= 0; --i) {
            suf[i] = max(suf[i + 1], startTime[i + 1] - endTime[i]);
        }

        int ans = 0;
        for (int i = 0; i < n; ++i) {
            int l = (i == 0) ? 0 : endTime[i - 1];
            int r = (i == n - 1) ? eventTime : startTime[i + 1];
            int w = endTime[i] - startTime[i];
            ans = max(ans, r - l - w);

            if (i > 0 && pre[i - 1] >= w) {
                ans = max(ans, r - l);
            } else if (i + 1 < n && suf[i + 1] >= w) {
                ans = max(ans, r - l);
            }
        }

        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxFreeTime(int eventTime, int[] startTime, int[] endTime) {
        int n = startTime.length;
        int[] pre = new int[n];
        int[] suf = new int[n];

        pre[0] = startTime[0];
        suf[n - 1] = eventTime - endTime[n - 1];

        for (int i = 1; i < n; i++) {
            pre[i] = Math.max(pre[i - 1], startTime[i] - endTime[i - 1]);
        }

        for (int i = n - 2; i >= 0; i--) {
            suf[i] = Math.max(suf[i + 1], startTime[i + 1] - endTime[i]);
        }

        int ans = 0;
        for (int i = 0; i < n; i++) {
            int l = (i == 0) ? 0 : endTime[i - 1];
            int r = (i == n - 1) ? eventTime : startTime[i + 1];
            int w = endTime[i] - startTime[i];
            ans = Math.max(ans, r - l - w);

            if (i > 0 && pre[i - 1] >= w) {
                ans = Math.max(ans, r - l);
            } else if (i + 1 < n && suf[i + 1] >= w) {
                ans = Math.max(ans, r - l);
            }
        }

        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxFreeTime(
        self, eventTime: int, startTime: List[int], endTime: List[int]
    ) -> int:
        n = len(startTime)
        pre = [0] * n
        suf = [0] * n
        pre[0] = startTime[0]
        suf[n - 1] = eventTime - endTime[-1]
        for i in range(1, n):
            pre[i] = max(pre[i - 1], startTime[i] - endTime[i - 1])
        for i in range(n - 2, -1, -1):
            suf[i] = max(suf[i + 1], startTime[i + 1] - endTime[i])
        ans = 0
        for i in range(n):
            l = 0 if i == 0 else endTime[i - 1]
            r = eventTime if i == n - 1 else startTime[i + 1]
            w = endTime[i] - startTime[i]
            ans = max(ans, r - l - w)
            if i and pre[i - 1] >= w:
                ans = max(ans, r - l)
            elif i + 1 < n and suf[i + 1] >= w:
                ans = max(ans, r - l)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
