# *132. Meeting Rooms III*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/meeting-rooms-iii/1)

## **🧩 Problem Description**

You are given an integer `n` representing the number of meeting rooms numbered from `0` to `n - 1`. You are also given a 2D integer array `meetings` where `meetings[i] = [start_i, end_i]` indicates that a meeting is scheduled during the half-open time interval `[start_i, end_i)`. All `start_i` values are unique.

**Meeting Allocation Rules:**

1. When a meeting starts, assign it to the available room with the smallest number.
2. If no rooms are free, delay the meeting until the earliest room becomes available. The delayed meeting retains its original duration.
3. When a room becomes free, assign it to the delayed meeting with the earliest original start time.

Return the room number that hosts the most meetings. If multiple rooms have the same highest number of meetings, return the smallest room number among them.

## Code(C++)
```cpp
class Solution {
public:
    int mostBooked(int n, vector<vector<int>>& meetings) {
        sort(meetings.begin(), meetings.end());
        priority_queue<int, vector<int>, greater<>> avail;
        priority_queue<pair<long long,int>, vector<pair<long long,int>>, greater<>> busy;
        vector<int> cnt(n);
        for(int i=0;i<n;i++) avail.push(i);
        for(auto &m:meetings){
            long long s=m[0], e=m[1];
            while(!busy.empty() && busy.top().first<=s){
                avail.push(busy.top().second);
                busy.pop();
            }
            int r = avail.empty() ? (busy.top().second) : avail.top();
            if(avail.empty()) {
                long long t=busy.top().first;
                busy.pop();
                busy.push({t+e-s, r});
            } else {
                avail.pop();
                busy.push({e, r});
            }
            cnt[r]++;
        }
        return max_element(cnt.begin(), cnt.end()) - cnt.begin();
    }
};
```

## Code (Java)

```java
class Solution {
    public int mostBooked(int n, int[][] A) {
        int[] cnt = new int[n];
        PriorityQueue<int[]> occ = new PriorityQueue<>((a, b) -> a[0] != b[0] ? Integer.compare(a[0], b[0]) : Integer.compare(a[1], b[1]));
        PriorityQueue<Integer> avail = new PriorityQueue<>();
        for (int i = 0; i < n; i++) avail.offer(i);
        Arrays.sort(A, (a, b) -> a[0] != b[0] ? Integer.compare(a[0], b[0]) : Integer.compare(a[1], b[1]));

        for (int[] m : A) {
            int s = m[0], e = m[1];
            while (!occ.isEmpty() && occ.peek()[0] <= s) avail.offer(occ.poll()[1]);
            if (!avail.isEmpty()) {
                int r = avail.poll();
                occ.offer(new int[]{e, r});
                cnt[r]++;
            } else {
                int[] t = occ.poll();
                occ.offer(new int[]{t[0] + e - s, t[1]});
                cnt[t[1]]++;
            }
        }

        int res = 0;
        for (int i = 1; i < n; i++) if (cnt[i] > cnt[res]) res = i;
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def mostBooked(self, n, A):
        A.sort()
        free = list(range(n))
        heapq.heapify(free)
        used = []
        cnt = [0] * n
        for s, e in A:
            while used and used[0][0] <= s:
                _, i = heapq.heappop(used)
                heapq.heappush(free, i)
            if not free:
                t, i = heapq.heappop(used)
                heapq.heappush(used, (t + e - s, i))
                cnt[i] += 1
            else:
                i = heapq.heappop(free)
                heapq.heappush(used, (e, i))
                cnt[i] += 1
        return cnt.index(max(cnt))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
