--- ❤️ ---

# 🚀 _Day 256. Minimum Cost to cut a board into squares_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/minimum-cost-to-cut-a-board-into-squares/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
using namespace std;

class Solution {
  public:
    int minCost(int n, int m, vector<int>& x, vector<int>& y) {
        // Sort in descending order
        sort(x.rbegin(), x.rend());
        sort(y.rbegin(), y.rend());
        
        int i = 0, j = 0;
        int horizontal_segments = 1;
        int vertical_segments = 1;
        long long cost = 0;
        int mod = 1e9 + 7;
        
        while (i < x.size() && j < y.size()) {
            if (x[i] >= y[j]) {
                cost = (cost + (long long)x[i] * horizontal_segments) % mod;
                vertical_segments++;
                i++;
            } else {
                cost = (cost + (long long)y[j] * vertical_segments) % mod;
                horizontal_segments++;
                j++;
            }
        }
        
        // Remaining vertical cuts
        while (i < x.size()) {
            cost = (cost + (long long)x[i] * horizontal_segments) % mod;
            i++;
        }
        
        // Remaining horizontal cuts
        while (j < y.size()) {
            cost = (cost + (long long)y[j] * vertical_segments) % mod;
            j++;
        }
        
        return cost;
    }
};

```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int minCost(int n, int m, ArrayList<Integer> x, ArrayList<Integer> y) {
        // Sort in descending order
        Collections.sort(x, Collections.reverseOrder());
        Collections.sort(y, Collections.reverseOrder());

        int i = 0, j = 0;
        int horizontalSegments = 1;
        int verticalSegments = 1;
        long cost = 0;
        int mod = (int)1e9 + 7;

        while (i < x.size() && j < y.size()) {
            if (x.get(i) >= y.get(j)) {
                cost = (cost + (long)x.get(i) * horizontalSegments) % mod;
                verticalSegments++;
                i++;
            } else {
                cost = (cost + (long)y.get(j) * verticalSegments) % mod;
                horizontalSegments++;
                j++;
            }
        }

        while (i < x.size()) {
            cost = (cost + (long)x.get(i) * horizontalSegments) % mod;
            i++;
        }

        while (j < y.size()) {
            cost = (cost + (long)y.get(j) * verticalSegments) % mod;
            j++;
        }

        return (int) cost;
    }
}

```

## Code (Python)

```python
def minCost(n, m, x, y):
    x.sort(reverse=True)
    y.sort(reverse=True)

    i = j = 0
    horizontal_segments = 1
    vertical_segments = 1
    cost = 0
    mod = 10**9 + 7

    while i < len(x) and j < len(y):
        if x[i] >= y[j]:
            cost = (cost + x[i] * horizontal_segments) % mod
            vertical_segments += 1
            i += 1
        else:
            cost = (cost + y[j] * vertical_segments) % mod
            horizontal_segments += 1
            j += 1

    while i < len(x):
        cost = (cost + x[i] * horizontal_segments) % mod
        i += 1

    while j < len(y):
        cost = (cost + y[j] * vertical_segments) % mod
        j += 1

    return cost

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
