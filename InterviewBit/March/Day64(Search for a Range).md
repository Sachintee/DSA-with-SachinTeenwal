--- ❤️ ---

# 🚀 _Day 64. Search for a Range_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/search-for-a-range/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    vector<int> searchRange(vector<int>& A, int B) {
        return {findFirstOccurrence(A, B), findLastOccurrence(A, B)};
    }

private:
    int findFirstOccurrence(vector<int>& A, int B) {
        int left = 0, right = A.size() - 1, result = -1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (A[mid] == B) {
                result = mid;
                right = mid - 1;  // Move left to find first occurrence
            } else if (A[mid] < B) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return result;
    }

    int findLastOccurrence(vector<int>& A, int B) {
        int left = 0, right = A.size() - 1, result = -1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (A[mid] == B) {
                result = mid;
                left = mid + 1;  // Move right to find last occurrence
            } else if (A[mid] < B) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return result;
    }
};

```

## Code (Java)

```java
class Solution {
    public int[] searchRange(int[] A, int B) {
        return new int[]{findFirstOccurrence(A, B), findLastOccurrence(A, B)};
    }

    private int findFirstOccurrence(int[] A, int B) {
        int left = 0, right = A.length - 1, result = -1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (A[mid] == B) {
                result = mid;
                right = mid - 1;  // Move left to find first occurrence
            } else if (A[mid] < B) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return result;
    }

    private int findLastOccurrence(int[] A, int B) {
        int left = 0, right = A.length - 1, result = -1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (A[mid] == B) {
                result = mid;
                left = mid + 1;  // Move right to find last occurrence
            } else if (A[mid] < B) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return result;
    }
}

```

## Code (Python)

```python
class Solution:
    def searchRange(self, A, B):
        def find_first_occurrence(A, B):
            left, right = 0, len(A) - 1
            result = -1
            while left <= right:
                mid = (left + right) // 2
                if A[mid] == B:
                    result = mid
                    right = mid - 1
                elif A[mid] < B:
                    left = mid + 1
                else:
                    right = mid - 1
            return result

        def find_last_occurrence(A, B):
            left, right = 0, len(A) - 1
            result = -1
            while left <= right:
                mid = (left + right) // 2
                if A[mid] == B:
                    result = mid
                    left = mid + 1
                elif A[mid] < B:
                    left = mid + 1
                else:
                    right = mid - 1
            return result

        first = find_first_occurrence(A, B)
        last = find_last_occurrence(A, B)
        return [first, last]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
