--- ❤️ ---

# 🚀 _Day 65. Rotated Sorted Array Search_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/rotated-sorted-array-search/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int search(vector<int>& A, int B) {
        int left = 0, right = A.size() - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (A[mid] == B) {
                return mid;
            }
            
            // Check if the left half is sorted
            if (A[left] <= A[mid]) {
                if (A[left] <= B && B < A[mid]) {
                    right = mid - 1;
                } else {
                    left = mid + 1;
                }
            }
            // Otherwise, the right half is sorted
            else {
                if (A[mid] < B && B <= A[right]) {
                    left = mid + 1;
                } else {
                    right = mid - 1;
                }
            }
        }
        
        return -1;
    }
};
```

## Code (Java)

```java
public class Solution {
    public int search(final int[] A, int B) {
        int left = 0, right = A.length - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (A[mid] == B) {
                return mid;
            }
            
            // Check if the left half is sorted
            if (A[left] <= A[mid]) {
                if (A[left] <= B && B < A[mid]) {
                    right = mid - 1;
                } else {
                    left = mid + 1;
                }
            }
            // Otherwise, the right half is sorted
            else {
                if (A[mid] < B && B <= A[right]) {
                    left = mid + 1;
                } else {
                    right = mid - 1;
                }
            }
        }
        
        return -1;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : tuple of integers
    # @param B : integer
    # @return an integer
    def search(self, A, B):
        left, right = 0, len(A) - 1
        
        while left <= right:
            mid = (left + right) // 2
            
            if A[mid] == B:
                return mid
            
            # Check if the left half is sorted
            if A[left] <= A[mid]:
                if A[left] <= B < A[mid]:
                    right = mid - 1
                else:
                    left = mid + 1
            # Otherwise, the right half is sorted
            else:
                if A[mid] < B <= A[right]:
                    left = mid + 1
                else:
                    right = mid - 1
        
        return -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
