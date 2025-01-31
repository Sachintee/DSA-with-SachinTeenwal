--- ❤️ ---

# 🚀 _Day 31. Merge Intervals_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/merge-intervals/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
using namespace std;

class Interval {
public:
    int start, end;
    Interval(int s, int e) : start(s), end(e) {}
};

class Solution {
public:
    vector<Interval> insert(vector<Interval>& intervals, Interval newInterval) {
        vector<Interval> merged;
        int i = 0, n = intervals.size();
        
        // Add intervals before newInterval
        while (i < n && intervals[i].end < newInterval.start) {
            merged.push_back(intervals[i]);
            i++;
        }
        
        // Merge overlapping intervals
        while (i < n && intervals[i].start <= newInterval.end) {
            newInterval.start = min(newInterval.start, intervals[i].start);
            newInterval.end = max(newInterval.end, intervals[i].end);
            i++;
        }
        merged.push_back(newInterval);
        
        // Add remaining intervals
        while (i < n) {
            merged.push_back(intervals[i]);
            i++;
        }
        
        return merged;
    }
};

// Driver Code
int main() {
    vector<Interval> intervals = {Interval(1, 3), Interval(6, 9)};
    Interval newInterval(2, 5);
    
    Solution obj;
    vector<Interval> result = obj.insert(intervals, newInterval);
    
    for (const auto& interval : result) {
        cout << "[" << interval.start << "," << interval.end << "] ";
    }
    return 0;
}

```

## Code (Java)

```java
import java.util.*;

class Interval {
    int start, end;
    Interval(int s, int e) {
        start = s;
        end = e;
    }
}

class Solution {
    public List<Interval> insert(List<Interval> intervals, Interval newInterval) {
        List<Interval> merged = new ArrayList<>();
        int i = 0, n = intervals.size();
        
        // Add all intervals before newInterval
        while (i < n && intervals.get(i).end < newInterval.start) {
            merged.add(intervals.get(i));
            i++;
        }
        
        // Merge overlapping intervals
        while (i < n && intervals.get(i).start <= newInterval.end) {
            newInterval.start = Math.min(newInterval.start, intervals.get(i).start);
            newInterval.end = Math.max(newInterval.end, intervals.get(i).end);
            i++;
        }
        merged.add(newInterval);
        
        // Add remaining intervals
        while (i < n) {
            merged.add(intervals.get(i));
            i++;
        }
        
        return merged;
    }

    public static void main(String[] args) {
        List<Interval> intervals = Arrays.asList(new Interval(1, 3), new Interval(6, 9));
        Interval newInterval = new Interval(2, 5);
        
        Solution obj = new Solution();
        List<Interval> result = obj.insert(intervals, newInterval);
        
        for (Interval interval : result) {
            System.out.print("[" + interval.start + "," + interval.end + "] ");
        }
    }
}

```

## Code (Python)

```python
# Definition for an interval.
class Interval:
    def __init__(self, s=0, e=0):
        self.start = s
        self.end = e

class Solution:
    def insert(self, intervals, new_interval):
        merged = []
        i = 0
        n = len(intervals)
        
        # Add all intervals before new_interval
        while i < n and intervals[i].end < new_interval.start:
            merged.append(intervals[i])
            i += 1
        
        # Merge overlapping intervals
        while i < n and intervals[i].start <= new_interval.end:
            new_interval.start = min(new_interval.start, intervals[i].start)
            new_interval.end = max(new_interval.end, intervals[i].end)
            i += 1
        merged.append(new_interval)
        
        # Add remaining intervals
        while i < n:
            merged.append(intervals[i])
            i += 1
        
        return merged

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>980</h4>
