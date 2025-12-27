--- ❤️ ---

# 🚀 _Day 361. Kth smallest element in a Matrix_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/kth-element-in-matrix/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int kthSmallest(vector<vector<int>> &mat, int k) {
        int n = mat.size();
        
        int low = mat[0][0];
        int high = mat[n - 1][n - 1];
        
        while (low < high) {
            int mid = low + (high - low) / 2;
            
            // Count elements <= mid
            int count = 0;
            int j = n - 1;
            
            for (int i = 0; i < n; i++) {
                while (j >= 0 && mat[i][j] > mid)
                    j--;
                count += (j + 1);
            }
            
            if (count < k)
                low = mid + 1;
            else
                high = mid;
        }
        
        return low;
    }
};

```

## Code (Java)

```java
class Solution {
    public int kthSmallest(int[][] mat, int k) {
        int n = mat.length;
        int low = mat[0][0];
        int high = mat[n - 1][n - 1];

        while (low < high) {
            int mid = low + (high - low) / 2;

            // count elements <= mid
            int count = 0;
            int j = n - 1;
            for (int i = 0; i < n; i++) {
                while (j >= 0 && mat[i][j] > mid) {
                    j--;
                }
                count += (j + 1);
            }

            if (count < k)
                low = mid + 1;
            else
                high = mid;
        }

        return low;
    }
}

```

## Code (Python)

```python
class Solution:
    def kthSmallest(self, mat, k):
        n = len(mat)
        low, high = mat[0][0], mat[n-1][n-1]

        while low < high:
            mid = (low + high) // 2

            # count elements <= mid
            count = 0
            j = n - 1
            for i in range(n):
                while j >= 0 and mat[i][j] > mid:
                    j -= 1
                count += (j + 1)

            if count < k:
                low = mid + 1
            else:
                high = mid

        return low

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
