--- ❤️ ---

# 🚀 _Day 67. Allocate Books_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/allocate-books/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
#include <numeric>
using namespace std;

class Solution {
public:
    int books(vector<int>& A, int B) {
        // Helper function to check if a given maximum pages is feasible
        auto isPossible = [&](int mid) {
            int students = 1;
            int currentPages = 0;
            for (int pages : A) {
                if (currentPages + pages > mid) {
                    students++;
                    currentPages = 0;
                }
                currentPages += pages;
            }
            return students <= B;
        };

        // Edge case: If number of students is greater than number of books
        if (B > A.size()) {
            return -1;
        }

        // Define the search space
        int left = *max_element(A.begin(), A.end()); // Minimum possible maximum pages
        int right = accumulate(A.begin(), A.end(), 0); // Maximum possible maximum pages

        // Binary search to find the minimum feasible maximum pages
        while (left < right) {
            int mid = left + (right - left) / 2;
            if (isPossible(mid)) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }

        return left;
    }
};
```

## Code (Java)

```java
import java.util.Arrays;

public class Solution {
    public int books(int[] A, int B) {
        // Helper function to check if a given maximum pages is feasible
        boolean isPossible(int mid) {
            int students = 1;
            int currentPages = 0;
            for (int pages : A) {
                if (currentPages + pages > mid) {
                    students++;
                    currentPages = 0;
                }
                currentPages += pages;
            }
            return students <= B;
        }

        // Edge case: If number of students is greater than number of books
        if (B > A.length) {
            return -1;
        }

        // Define the search space
        int left = Arrays.stream(A).max().getAsInt(); // Minimum possible maximum pages
        int right = Arrays.stream(A).sum(); // Maximum possible maximum pages

        // Binary search to find the minimum feasible maximum pages
        while (left < right) {
            int mid = left + (right - left) / 2;
            if (isPossible(mid)) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }

        return left;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @param B : integer
    # @return an integer
    def books(self, A, B):
        # Helper function to check if a given maximum pages is feasible
        def is_possible(mid):
            students = 1
            current_pages = 0
            for pages in A:
                if current_pages + pages > mid:
                    students += 1
                    current_pages = 0
                current_pages += pages
            return students <= B

        # Edge case: If number of students is greater than number of books
        if B > len(A):
            return -1

        # Define the search space
        left = max(A)  # Minimum possible maximum pages
        right = sum(A)  # Maximum possible maximum pages

        # Binary search to find the minimum feasible maximum pages
        while left < right:
            mid = (left + right) // 2
            if is_possible(mid):
                right = mid
            else:
                left = mid + 1

        return left
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
