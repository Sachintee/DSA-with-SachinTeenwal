--- ❤️ ---

# 🚀 _Day 360. Kth Missing Positive Number in a Sorted Array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/kth-missing-positive-number-in-a-sorted-array/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    int kthMissing(vector<int> &arr, int k) {
        int n = arr.size();
        
        // If kth missing is before the first element
        if (arr[0] > k)
            return k;
        
        int low = 0, high = n - 1;
        
        while (low <= high) {
            int mid = low + (high - low) / 2;
            
            int missing = arr[mid] - (mid + 1);
            
            if (missing < k)
                low = mid + 1;
            else
                high = mid - 1;
        }
        
        // kth missing number
        return k + high + 1;
    }
};

```

## Code (Java)

```java
class Solution {
    public int kthMissing(int[] arr, int k) {
        int n = arr.length;

        // If kth missing is before the first element
        if (arr[0] > k)
            return k;

        int low = 0, high = n - 1;

        while (low <= high) {
            int mid = low + (high - low) / 2;
            int missing = arr[mid] - (mid + 1);

            if (missing < k)
                low = mid + 1;
            else
                high = mid - 1;
        }

        return k + high + 1;
    }
}

```

## Code (Python3)

```python
class Solution:
    def kthMissing(self, arr, k):
        n = len(arr)

        # If kth missing is before the first element
        if arr[0] > k:
            return k

        low, high = 0, n - 1

        while low <= high:
            mid = (low + high) // 2
            missing = arr[mid] - (mid + 1)

            if missing < k:
                low = mid + 1
            else:
                high = mid - 1

        return k + high + 1

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
