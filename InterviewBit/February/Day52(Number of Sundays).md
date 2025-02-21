--- ❤️ ---

# 🚀 _Day 52. Number of Sundays_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/number-of-sundays/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
#include <vector>

using namespace std;

class Solution {
public:
    int solve(string A, int B) {
        vector<string> days = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"};
        
        // Find the index of the start day
        int start_index = 0;
        for (int i = 0; i < days.size(); i++) {
            if (days[i] == A) {
                start_index = i;
                break;
            }
        }
        
        // Calculate the first Sunday
        int first_sunday = (7 - start_index) % 7;
        if (first_sunday == 0) {
            first_sunday = 7;
        }
        
        // If the month has fewer days than the first Sunday, return 0
        if (B < first_sunday) {
            return 0;
        }
        
        // Calculate the total number of Sundays
        return 1 + (B - first_sunday) / 7;
    }
};

int main() {
    Solution sol;
    cout << sol.solve("Sunday", 1) << endl; // Output: 1
    cout << sol.solve("Monday", 14) << endl; // Output: 2
    return 0;
}
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(String A, int B) {
        String[] days = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"};
        
        // Find the index of the start day
        int startIndex = 0;
        for (int i = 0; i < days.length; i++) {
            if (days[i].equals(A)) {
                startIndex = i;
                break;
            }
        }
        
        // Calculate the first Sunday
        int firstSunday = (7 - startIndex) % 7;
        if (firstSunday == 0) {
            firstSunday = 7;
        }
        
        // If the month has fewer days than the first Sunday, return 0
        if (B < firstSunday) {
            return 0;
        }
        
        // Calculate the total number of Sundays
        return 1 + (B - firstSunday) / 7;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        System.out.println(sol.solve("Sunday", 1)); // Output: 1
        System.out.println(sol.solve("Monday", 14)); // Output: 2
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        # Days of the week in order
        days = ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"]
        
        # Find the index of the start day
        start_index = days.index(A)
        
        # Calculate the number of Sundays
        # The first Sunday is at (7 - start_index) % 7 days from the start
        # Then, every 7 days after that is a Sunday
        # Total Sundays = 1 (for the first Sunday) + (B - (7 - start_index)) // 7
        first_sunday = (7 - start_index) % 7
        if first_sunday == 0:
            first_sunday = 7
        
        if B < first_sunday:
            return 0
        
        return 1 + (B - first_sunday) // 7
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
