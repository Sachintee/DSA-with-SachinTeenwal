--- ❤️ ---

# 🚀 _Day 349. Count Indices to Balance Even and Odd Sums_ 🧠

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/count-indices-to-balance-even-and-odd-sums/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int cntWays(vector<int>& arr) {
        int n = arr.size();

        vector<long long> prefEven(n + 1, 0), prefOdd(n + 1, 0);

        // Prefix sums
        for (int i = 0; i < n; i++) {
            prefEven[i + 1] = prefEven[i];
            prefOdd[i + 1] = prefOdd[i];

            if (i % 2 == 0)
                prefEven[i + 1] += arr[i];
            else
                prefOdd[i + 1] += arr[i];
        }

        long long totalEven = prefEven[n];
        long long totalOdd = prefOdd[n];

        int count = 0;

        for (int i = 0; i < n; i++) {
            long long pe = prefEven[i];
            long long po = prefOdd[i];

            long long se, so;
            if (i % 2 == 0) {
                se = totalOdd - prefOdd[i + 1];
                so = totalEven - prefEven[i + 1];
            } else {
                se = totalOdd - prefOdd[i + 1];
                so = totalEven - prefEven[i + 1];
            }

            if (pe + se == po + so)
                count++;
        }

        return count;
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
