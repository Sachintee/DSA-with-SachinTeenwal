--- ❤️ ---

# 🚀 _Day 60. Search in Bitonic Array!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/search-in-bitonic-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    int solve(vector<int>& A, int B) {
        // Find the bitonic point (peak element)
        int bitonicPoint = findBitonicPoint(A);
        
        // Search in the ascending part
        int result = ascendingBinarySearch(A, 0, bitonicPoint, B);
        if (result != -1) {
            return result;
        }
        
        // Search in the descending part
        result = descendingBinarySearch(A, bitonicPoint + 1, A.size() - 1, B);
        return result;
    }

private:
    // Function to find the bitonic point (peak element)
    int findBitonicPoint(vector<int>& arr) {
        int low = 0, high = arr.size() - 1;
        while (low < high) {
            int mid = low + (high - low) / 2;
            if (arr[mid] > arr[mid + 1]) {
                high = mid;
            } else {
                low = mid + 1;
            }
        }
        return low;
    }

    // Binary search for ascending part of the array
    int ascendingBinarySearch(vector<int>& arr, int low, int high, int target) {
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (arr[mid] == target) {
                return mid;
            } else if (arr[mid] < target) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        return -1;
    }

    // Binary search for descending part of the array
    int descendingBinarySearch(vector<int>& arr, int low, int high, int target) {
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (arr[mid] == target) {
                return mid;
            } else if (arr[mid] < target) {
                high = mid - 1;
            } else {
                low = mid + 1;
            }
        }
        return -1;
    }
};
```

## Code (Java)

```java
import java.util.List;

public class Solution {
    public int solve(List<Integer> A, int B) {
        // Find the bitonic point (peak element)
        int bitonicPoint = findBitonicPoint(A);
        
        // Search in the ascending part
        int result = ascendingBinarySearch(A, 0, bitonicPoint, B);
        if (result != -1) {
            return result;
        }
        
        // Search in the descending part
        result = descendingBinarySearch(A, bitonicPoint + 1, A.size() - 1, B);
        return result;
    }

    // Function to find the bitonic point (peak element)
    private int findBitonicPoint(List<Integer> arr) {
        int low = 0, high = arr.size() - 1;
        while (low < high) {
            int mid = low + (high - low) / 2;
            if (arr.get(mid) > arr.get(mid + 1)) {
                high = mid;
            } else {
                low = mid + 1;
            }
        }
        return low;
    }

    // Binary search for ascending part of the array
    private int ascendingBinarySearch(List<Integer> arr, int low, int high, int target) {
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (arr.get(mid) == target) {
                return mid;
            } else if (arr.get(mid) < target) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        return -1;
    }

    // Binary search for descending part of the array
    private int descendingBinarySearch(List<Integer> arr, int low, int high, int target) {
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (arr.get(mid) == target) {
                return mid;
            } else if (arr.get(mid) < target) {
                high = mid - 1;
            } else {
                low = mid + 1;
            }
        }
        return -1;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        # Find the bitonic point (peak element)
        def find_bitonic_point(arr):
            low, high = 0, len(arr) - 1
            while low < high:
                mid = (low + high) // 2
                if arr[mid] > arr[mid + 1]:
                    high = mid
                else:
                    low = mid + 1
            return low
        
        # Binary search for ascending part of the array
        def ascending_binary_search(arr, low, high, target):
            while low <= high:
                mid = (low + high) // 2
                if arr[mid] == target:
                    return mid
                elif arr[mid] < target:
                    low = mid + 1
                else:
                    high = mid - 1
            return -1
        
        # Binary search for descending part of the array
        def descending_binary_search(arr, low, high, target):
            while low <= high:
                mid = (low + high) // 2
                if arr[mid] == target:
                    return mid
                elif arr[mid] < target:
                    high = mid - 1
                else:
                    low = mid + 1
            return -1
        
        # Find the bitonic point
        bitonic_point = find_bitonic_point(A)
        
        # Search in the ascending part
        result = ascending_binary_search(A, 0, bitonic_point, B)
        if result != -1:
            return result
        
        # Search in the descending part
        result = descending_binary_search(A, bitonic_point + 1, len(A) - 1, B)
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
