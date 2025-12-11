--- ❤️ ---

# 🚀 _Day 345. Construct an array from its pair-sum array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/construct-an-array-from-its-pair-sum-array/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> constructArr(vector<int>& arr) {
        int m = arr.size();

        // If arr size is 1, solution array is of size 2
        if (m == 1) {
            return {1, arr[0] - 1}; 
        }

        // Find n using m = n*(n-1)/2
        int n = (1 + sqrt(1 + 8 * m)) / 2;

        vector<int> res(n);

        long long S01 = arr[0];
        long long S02 = arr[1];
        long long S12 = arr[n - 1];  // This is S12

        // Compute first three elements
        res[0] = (S01 + S02 - S12) / 2;
        res[1] = S01 - res[0];
        res[2] = S02 - res[0];

        // Compute rest: arr index increases sequentially
        int k = 2;
        for (int i = 3; i < n; i++) {
            k++;
            res[i] = arr[k - 1] - res[0];
        }

        return res;
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
