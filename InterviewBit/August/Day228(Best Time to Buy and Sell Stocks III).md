--- ❤️ ---

# 🚀 _Day 228. Best Time to Buy and Sell Stocks III_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/best-time-to-buy-and-sell-stocks-iii/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <climits>
#include <algorithm>

using namespace std;

class Solution {
public:
    int maxProfit(vector<int>& prices) {
        if (prices.size() < 2) return 0;
        
        int firstBuy = INT_MIN;
        int firstSell = 0;
        int secondBuy = INT_MIN;
        int secondSell = 0;
        
        for (int price : prices) {
            firstBuy = max(firstBuy, -price);
            firstSell = max(firstSell, firstBuy + price);
            secondBuy = max(secondBuy, firstSell - price);
            secondSell = max(secondSell, secondBuy + price);
        }
        
        return secondSell;
    }
};
```

## Code (Java)

```java
public class Solution {
    public int maxProfit(int[] prices) {
        if (prices == null || prices.length < 2) return 0;
        
        int firstBuy = Integer.MIN_VALUE;
        int firstSell = 0;
        int secondBuy = Integer.MIN_VALUE;
        int secondSell = 0;
        
        for (int price : prices) {
            firstBuy = Math.max(firstBuy, -price);
            firstSell = Math.max(firstSell, firstBuy + price);
            secondBuy = Math.max(secondBuy, firstSell - price);
            secondSell = Math.max(secondSell, secondBuy + price);
        }
        
        return secondSell;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxProfit(self, A):
        if not A or len(A) < 2:
            return 0
        
        first_buy = -float('inf')
        first_sell = 0
        second_buy = -float('inf')
        second_sell = 0
        
        for price in A:
            first_buy = max(first_buy, -price)
            first_sell = max(first_sell, first_buy + price)
            second_buy = max(second_buy, first_sell - price)
            second_sell = max(second_sell, second_buy + price)
        
        return second_sell
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
