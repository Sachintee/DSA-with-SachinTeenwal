--- ❤️ ---

# 🚀 _Day 314. Stock Buy and Sell with Cooldown_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/buy-stock-with-cooldown/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    int maxProfit(vector<int>& arr) {
        int n = arr.size();
        if (n == 0) return 0;

        vector<int> hold(n, 0), sell(n, 0), rest(n, 0);
        hold[0] = -arr[0];
        sell[0] = 0;
        rest[0] = 0;

        for (int i = 1; i < n; i++) {
            hold[i] = max(hold[i-1], rest[i-1] - arr[i]);
            sell[i] = hold[i-1] + arr[i];
            rest[i] = max(rest[i-1], sell[i-1]);
        }

        return max(sell[n-1], rest[n-1]);
    }
};

```

## Code (Java)

```java
class Solution {
    public int maxProfit(int[] arr) {
        if (arr.length == 0) return 0;

        int hold = -arr[0];  // holding a stock
        int sell = 0;        // just sold a stock
        int rest = 0;        // in cooldown or idle

        for (int i = 1; i < arr.length; i++) {
            int prev_hold = hold;
            int prev_sell = sell;
            int prev_rest = rest;

            hold = Math.max(prev_hold, prev_rest - arr[i]); // buy or hold
            sell = prev_hold + arr[i];                      // sell today
            rest = Math.max(prev_rest, prev_sell);          // cooldown or stay idle
        }

        // can't end while holding a stock
        return Math.max(sell, rest);
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        int[] arr1 = {0, 2, 1, 2, 3};
        int[] arr2 = {3, 1, 6, 1, 2, 4};

        System.out.println(sol.maxProfit(arr1)); // Output: 3
        System.out.println(sol.maxProfit(arr2)); // Output: 7
    }
}

```

## Code (Python)

```python
class Solution:
    def maxProfit(self, arr):
        if not arr:
            return 0

        hold = -arr[0]  # currently holding a stock
        sell = 0        # just sold a stock
        rest = 0        # in cooldown or idle

        for i in range(1, len(arr)):
            prev_hold = hold
            prev_sell = sell
            prev_rest = rest

            hold = max(prev_hold, prev_rest - arr[i])  # buy or hold
            sell = prev_hold + arr[i]                  # sell today
            rest = max(prev_rest, prev_sell)           # cooldown or rest

        # can't end while holding stock
        return max(sell, rest)


# Driver code
sol = Solution()
print(sol.maxProfit([0, 2, 1, 2, 3]))   # Output: 3
print(sol.maxProfit([3, 1, 6, 1, 2, 4]))  # Output: 7

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
