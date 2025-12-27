--- ❤️ ---

# 🚀 _Day 361. Meeting Rooms III_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/meeting-rooms-iii/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int mostBooked(int n, vector<vector<int>>& meetings) {
        sort(meetings.begin(), meetings.end());
        using pli = pair<long long, int>;
        priority_queue<pli, vector<pli>, greater<pli>> busy;
        priority_queue<int, vector<int>, greater<int>> idle;
        for (int i = 0; i < n; ++i) {
            idle.push(i);
        }
        vector<int> cnt(n);
        for (auto& v : meetings) {
            int s = v[0], e = v[1];
            while (!busy.empty() && busy.top().first <= s) {
                idle.push(busy.top().second);
                busy.pop();
            }
            int i = 0;
            if (!idle.empty()) {
                i = idle.top();
                idle.pop();
                busy.push({e, i});
            } else {
                auto x = busy.top();
                busy.pop();
                i = x.second;
                busy.push({x.first + e - s, i});
            }
            ++cnt[i];
        }
        int ans = 0;
        for (int i = 0; i < n; ++i) {
            if (cnt[ans] < cnt[i]) {
                ans = i;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int mostBooked(int n, int[][] meetings) {
        Arrays.sort(meetings, (a, b) -> a[0] - b[0]);
        PriorityQueue<int[]> busy
            = new PriorityQueue<>((a, b) -> a[0] == b[0] ? a[1] - b[1] : a[0] - b[0]);
        PriorityQueue<Integer> idle = new PriorityQueue<>();
        for (int i = 0; i < n; ++i) {
            idle.offer(i);
        }
        int[] cnt = new int[n];
        for (var v : meetings) {
            int s = v[0], e = v[1];
            while (!busy.isEmpty() && busy.peek()[0] <= s) {
                idle.offer(busy.poll()[1]);
            }
            int i = 0;
            if (!idle.isEmpty()) {
                i = idle.poll();
                busy.offer(new int[] {e, i});
            } else {
                var x = busy.poll();
                i = x[1];
                busy.offer(new int[] {x[0] + e - s, i});
            }
            ++cnt[i];
        }
        int ans = 0;
        for (int i = 0; i < n; ++i) {
            if (cnt[ans] < cnt[i]) {
                ans = i;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def mostBooked(self, n: int, meetings: List[List[int]]) -> int:
        meetings.sort(key=lambda x: x[0])
        busy = []
        idle = list(range(n))
        heapify(idle)
        cnt = [0] * n
        for s, e in meetings:
            while busy and busy[0][0] <= s:
                heappush(idle, heappop(busy)[1])
            i = 0
            if idle:
                i = heappop(idle)
                heappush(busy, (e, i))
            else:
                time_end, i = heappop(busy)
                heappush(busy, (time_end + e - s, i))
            cnt[i] += 1
        ans = 0
        for i in range(n):
            if cnt[ans] < cnt[i]:
                ans = i
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
