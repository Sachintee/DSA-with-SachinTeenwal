---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Stack
  - Arrays
---

# 🚀 _Day 55. Stock span problem_ 🧠 


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/stack-gfg-160/problem/stock-span-problem-1587115621)  

## 💡 **Problem Description:**  

The **Stock Span Problem** is a financial problem where we have a series of **daily stock prices**, and we need to compute the **span of each day's stock price**.  

The **span of stock price on a given day i** is defined as the **maximum number of consecutive days** just before day `i`, for which the price of the stock on the given day is **less than or equal to its price on the current day**.  


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> calculateSpan(vector<int>& arr) {
        vector<int> span(arr.size());
        stack<int> st;
        
        for (int i = 0; i < arr.size(); i++) {
            while (!st.empty() && arr[st.top()] <= arr[i]) st.pop();
            span[i] = st.empty() ? i + 1 : i - st.top();
            st.push(i);
        }
        return span;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> calculateSpan(int[] arr) {
        ArrayList<Integer> span = new ArrayList<>();
        Stack<Integer> st = new Stack<>();
        
        for (int i = 0; i < arr.length; i++) {
            int days = 1;
            while (!st.isEmpty() && arr[st.peek()] <= arr[i]) {
                days += span.get(st.pop());
            }
            span.add(days);
            st.push(i);
        }
        return span;
    }
}
```

## Code (Python)

```python
class Solution:
    def calculateSpan(self, arr):
        span, st = [], []
        
        for i, price in enumerate(arr):
            days = 1
            while st and arr[st[-1]] <= price:
                days += span[st.pop()]
            span.append(days)
            st.append(i)
        
        return span
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
