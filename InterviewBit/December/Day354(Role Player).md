--- ❤️ ---

# 🚀 _Day 354. Role Player_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/role-player/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int searchInsertK(vector<int> &arr, int k) {
        int low = 0, high = arr.size() - 1;
        
        while (low <= high) {
            int mid = low + (high - low) / 2;
            
            if (arr[mid] == k)
                return mid;
            else if (arr[mid] < k)
                low = mid + 1;
            else
                high = mid - 1;
        }
        
        // low is the correct insert position
        return low;
    }
};

```

## Code (Java)

```java

```

## Code (Python)

```python

```
## Code (SQL)
'''sql
SELECT 
    CONCAT(Player, '(', LEFT(Role, 1), ')') AS N
FROM GAMERS
ORDER BY Player ASC;
'''


## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
