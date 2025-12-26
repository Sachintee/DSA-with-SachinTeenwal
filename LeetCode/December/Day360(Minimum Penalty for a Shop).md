--- ❤️ ---

# 🚀 _Day 360. Minimum Penalty for a Shop_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-penalty-for-a-shop/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int bestClosingTime(string customers) {
        int ans = 0;
        int cost = 0;
        for (char c : customers) {
            if (c == 'Y') {
                cost++;
            }
        }
        int mn = cost;
        for (int j = 1; j <= customers.size(); ++j) {
            cost += customers[j - 1] == 'N' ? 1 : -1;
            if (cost < mn) {
                ans = j;
                mn = cost;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int bestClosingTime(String customers) {
        int n = customers.length();
        int ans = 0, cost = 0;
        for (int i = 0; i < n; i++) {
            if (customers.charAt(i) == 'Y') {
                cost++;
            }
        }
        int mn = cost;
        for (int j = 1; j <= n; j++) {
            cost += customers.charAt(j - 1) == 'N' ? 1 : -1;
            if (cost < mn) {
                ans = j;
                mn = cost;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def bestClosingTime(self, customers: str) -> int:
        ans = 0
        mn = cost = customers.count("Y")
        for j, c in enumerate(customers, 1):
            cost += 1 if c == "N" else -1
            if cost < mn:
                ans, mn = j, cost
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
