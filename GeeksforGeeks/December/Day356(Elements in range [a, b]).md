--- ❤️ ---

# 🚀 _Day 356. Elements in range [a, b]_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/find-number-of-elements-in-range-a-b-for-each-query/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> cntInRange(vector<int> &arr, vector<vector<int>> &queries) {
        // Step 1: Sort the array
        sort(arr.begin(), arr.end());
        
        vector<int> result;
        
        // Step 2: Process each query
        for (auto &q : queries) {
            int a = q[0];
            int b = q[1];
            
            // Count elements in range [a, b]
            int count = upper_bound(arr.begin(), arr.end(), b)
                        - lower_bound(arr.begin(), arr.end(), a);
            
            result.push_back(count);
        }
        
        return result;
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
