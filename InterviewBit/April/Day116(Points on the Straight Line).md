--- ❤️ ---

# 🚀 _Day 116. Points on the Straight Line_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/points-on-the-straight-line/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <unordered_map>
#include <algorithm>
#include <climits>

using namespace std;

class Solution {
public:
    int maxPoints(vector<int>& A, vector<int>& B) {
        if (A.size() <= 2) return A.size();
        
        int max_points = 0;
        
        for (int i = 0; i < A.size(); ++i) {
            unordered_map<string, int> slope_counts;
            int duplicates = 0;
            int current_max = 0;
            
            for (int j = 0; j < A.size(); ++j) {
                if (i == j) continue;
                
                int x1 = A[i], y1 = B[i];
                int x2 = A[j], y2 = B[j];
                
                if (x1 == x2 && y1 == y2) {
                    duplicates++;
                    continue;
                }
                
                string slope;
                if (x1 == x2) {
                    slope = "inf";
                } else {
                    int delta_y = y2 - y1;
                    int delta_x = x2 - x1;
                    int gcd_val = gcd(delta_y, delta_x);
                    slope = to_string(delta_y / gcd_val) + "_" + to_string(delta_x / gcd_val);
                }
                
                slope_counts[slope]++;
                current_max = max(current_max, slope_counts[slope]);
            }
            
            max_points = max(max_points, current_max + duplicates + 1);
        }
        
        return max_points;
    }
    
private:
    int gcd(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }
};
```

## Code (Java)

```java
import java.util.HashMap;
import java.util.Map;

public class Solution {
    public int maxPoints(int[] A, int[] B) {
        if (A.length <= 2) return A.length;
        
        int maxPoints = 0;
        
        for (int i = 0; i < A.length; i++) {
            Map<String, Integer> slopeCounts = new HashMap<>();
            int duplicates = 0;
            int currentMax = 0;
            
            for (int j = 0; j < A.length; j++) {
                if (i == j) continue;
                
                int x1 = A[i], y1 = B[i];
                int x2 = A[j], y2 = B[j];
                
                if (x1 == x2 && y1 == y2) {
                    duplicates++;
                    continue;
                }
                
                String slope;
                if (x1 == x2) {
                    slope = "inf";
                } else {
                    int deltaY = y2 - y1;
                    int deltaX = x2 - x1;
                    int gcdVal = gcd(deltaY, deltaX);
                    slope = (deltaY / gcdVal) + "_" + (deltaX / gcdVal);
                }
                
                slopeCounts.put(slope, slopeCounts.getOrDefault(slope, 0) + 1);
                currentMax = Math.max(currentMax, slopeCounts.get(slope));
            }
            
            maxPoints = Math.max(maxPoints, currentMax + duplicates + 1);
        }
        
        return maxPoints;
    }
    
    private int gcd(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }
}
```

## Code (Python)

```python
from collections import defaultdict

def gcd(a, b):
    while b:
        a, b = b, a % b
    return a

class Solution:
    # @param A : list of integers
    # @param B : list of integers
    # @return an integer
    def maxPoints(self, A, B):
        if len(A) <= 2:
            return len(A)
        
        max_points = 0
        
        for i in range(len(A)):
            x1, y1 = A[i], B[i]
            slope_counts = defaultdict(int)
            duplicates = 0
            current_max = 0
            
            for j in range(len(A)):
                if i == j:
                    continue
                
                x2, y2 = A[j], B[j]
                
                if x1 == x2 and y1 == y2:
                    duplicates += 1
                    continue
                
                if x1 == x2:
                    slope = 'inf'
                else:
                    delta_y = y2 - y1
                    delta_x = x2 - x1
                    gcd_val = gcd(delta_y, delta_x)
                    slope = (delta_y // gcd_val, delta_x // gcd_val)
                
                slope_counts[slope] += 1
                current_max = max(current_max, slope_counts[slope])
            
            max_points = max(max_points, current_max + duplicates + 1)
        
        return max_points
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
