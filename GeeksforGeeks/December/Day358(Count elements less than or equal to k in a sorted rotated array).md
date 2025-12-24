--- ❤️ ---

# 🚀 _Day 358. Count elements less than or equal to k in a sorted rotated array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/count-elements-less-than-or-equal-to-k-in-a-sorted-rotated-array/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countLessEqual(vector<int>& arr, int x) {
        int n = arr.size();
        
        // Step 1: Find index of minimum element (rotation point)
        int low = 0, high = n - 1;
        while (low < high) {
            int mid = low + (high - low) / 2;
            if (arr[mid] > arr[high])
                low = mid + 1;
            else
                high = mid;
        }
        int pivot = low;

        // Step 2: Count elements ≤ x in both sorted halves
        int count = 0;
        
        // Left sorted part [0 ... pivot-1]
        count += upper_bound(arr.begin(), arr.begin() + pivot, x) - arr.begin();
        
        // Right sorted part [pivot ... n-1]
        count += upper_bound(arr.begin() + pivot, arr.end(), x) - (arr.begin() + pivot);

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
