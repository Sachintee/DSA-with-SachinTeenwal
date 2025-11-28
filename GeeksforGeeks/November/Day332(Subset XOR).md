--- ❤️ ---

# 🚀 _Day 332. Subset XOR_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/subset-xor--175953/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> subsetXOR(int n) {

        // Compute XOR from 1 to n using pattern
        int X;
        if (n % 4 == 0) X = n;
        else if (n % 4 == 1) X = 1;
        else if (n % 4 == 2) X = n + 1;
        else X = 0; // n % 4 == 3

        // If XOR(1..n) == n → full set is answer
        if (X == n) {
            vector<int> ans(n);
            for (int i = 1; i <= n; i++) ans[i-1] = i;
            return ans;
        }

        // Otherwise remove element v = X ^ n
        int v = X ^ n;

        vector<int> ans;
        for (int i = 1; i <= n; i++) {
            if (i != v)
                ans.push_back(i);
        }

        return ans;
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
