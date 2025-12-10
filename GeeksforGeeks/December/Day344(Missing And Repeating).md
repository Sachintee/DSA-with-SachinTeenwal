--- ❤️ ---

# 🚀 _Day 344. Missing And Repeating_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/find-missing-and-repeating2512/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> findTwoElement(vector<int>& arr) {
        long long n = arr.size();
        long long sumN = n * (n + 1) / 2;
        long long sumSqN = n * (n + 1) * (2 * n + 1) / 6;

        long long sum = 0, sumSq = 0;
        for (long long x : arr) {
            sum += x;
            sumSq += 1LL * x * x;
        }

        long long diff = sum - sumN;                  // R - M
        long long diffSq = sumSq - sumSqN;            // R^2 - M^2 = (R - M)(R + M)

        long long sumRM = diffSq / diff;              // R + M

        long long repeating = (diff + sumRM) / 2;
        long long missing = repeating - diff;

        return {(int)repeating, (int)missing};
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
