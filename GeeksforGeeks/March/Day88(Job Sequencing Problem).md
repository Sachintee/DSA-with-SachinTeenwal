---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Greedy
  - Dynamic Programming
---

# 🚀 _Day 88. Job Sequencing Problem_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/greedy-gfg-160/problem/job-sequencing-problem-1587115620)  

> Note: Sorry for uploading late, my exam is going on.


## 💡 **Problem Description:** 

You are given two arrays: **deadline[]** and **profit[]**, which represent a set of jobs. Each job:  
- Has a **deadline** by which it must be completed.  
- Has a **profit** associated with it.  
- Takes **exactly one unit of time** to complete.  
- Only **one job** can be scheduled at a time.  
## Code(C++)
```cpp
class Solution {
public:
    vector<int> jobSequencing(vector<int>& d, vector<int>& p) {
        vector<pair<int, int>> jobs;
        for (int i = 0; i < d.size(); ++i) jobs.emplace_back(d[i], p[i]);
        sort(jobs.begin(), jobs.end());

        priority_queue<int, vector<int>, greater<int>> pq;
        for (const auto& job : jobs) {
            if (job.first > pq.size()) pq.push(job.second);
            else if (pq.top() < job.second) pq.pop(), pq.push(job.second);
        }

        int cnt = pq.size(), tot = 0;
        while (!pq.empty()) tot += pq.top(), pq.pop();
        return {cnt, tot};
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> jobSequencing(int[] d, int[] p) {
        int n = d.length, cnt = 0, tot = 0;
        PriorityQueue<Integer> pq = new PriorityQueue<>();
        List<int[]> jobs = new ArrayList<>();
        
        for (int i = 0; i < n; i++) jobs.add(new int[] {d[i], p[i]});
        jobs.sort(Comparator.comparingInt(a -> a[0]));

        for (int[] job : jobs) {
            if (job[0] > pq.size()) pq.add(job[1]);
            else if (pq.peek() < job[1]) { pq.poll(); pq.add(job[1]); }
        }
        
        cnt = pq.size();
        while (!pq.isEmpty()) tot += pq.poll();
        
        return new ArrayList<>(Arrays.asList(cnt, tot));
    }
}
```

## Code (Python)

```python
from heapq import heappush, heappop

class Solution:
    def jobSequencing(self, d, p):
        jobs = sorted(zip(d, p))
        pq = []

        for deadline, profit in jobs:
            if len(pq) < deadline:
                heappush(pq, profit)
            elif pq and pq[0] < profit:
                heappop(pq)
                heappush(pq, profit)

        return [len(pq), sum(pq)]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
