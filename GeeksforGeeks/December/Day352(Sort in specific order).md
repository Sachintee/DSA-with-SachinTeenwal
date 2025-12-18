--- ❤️ ---

# 🚀 _Day 352. Sort in specific order_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/sort-in-specific-order2422/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    void sortIt(vector<int>& arr) {
        vector<int> odd, even;

        // Separate odd and even numbers
        for (int x : arr) {
            if (x % 2 == 1)
                odd.push_back(x);
            else
                even.push_back(x);
        }

        // Sort odd in descending order
        sort(odd.begin(), odd.end(), greater<int>());

        // Sort even in ascending order
        sort(even.begin(), even.end());

        // Merge back into arr
        int idx = 0;
        for (int x : odd) arr[idx++] = x;
        for (int x : even) arr[idx++] = x;
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
