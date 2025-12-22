--- ❤️ ---

# 🚀 _Day 356. Row with max 1s_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/row-with-max-1s0023/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    int rowWithMax1s(vector<vector<int>> &arr) {
        int n = arr.size();
        int m = arr[0].size();
        
        int maxRowIndex = -1;
        int j = m - 1;  // start from top-right corner
        
        for (int i = 0; i < n; i++) {
            while (j >= 0 && arr[i][j] == 1) {
                maxRowIndex = i;
                j--;  // move left
            }
        }
        
        return maxRowIndex;
    }
};

```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
