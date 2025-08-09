--- ❤️ ---

# 🚀 _Day 221. Min Jumps Array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/min-jumps-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

int minJumps(vector<int>& A) {
    int n = A.size();
    if (n <= 1) return 0;
    if (A[0] == 0) return -1;

    int jumps = 0;
    int farthest = 0;
    int end = 0;

    for (int i = 0; i < n - 1; i++) {
        farthest = max(farthest, i + A[i]);
        if (i == end) {
            jumps++;
            end = farthest;
            if (end >= n - 1) break;
        }
    }

    return (end >= n - 1) ? jumps : -1;
}

int main() {
    vector<int> A = {2, 3, 1, 1, 4};
    cout << minJumps(A) << endl; // Output: 2
    return 0;
}

```

## Code (Java)

```java
public class Solution {
    public int jump(int[] A) {
        int n = A.length;
        if (n <= 1) return 0;
        if (A[0] == 0) return -1;

        int jumps = 0;
        int farthest = 0;
        int end = 0;

        for (int i = 0; i < n - 1; i++) {
            farthest = Math.max(farthest, i + A[i]);
            if (i == end) {
                jumps++;
                end = farthest;
                if (end >= n - 1) break;
            }
        }

        return (end >= n - 1) ? jumps : -1;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        int[] A = {2, 3, 1, 1, 4};
        System.out.println(sol.jump(A)); // Output: 2
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return an integer
    def jump(self, A):
        n = len(A)
        if n <= 1:
            return 0
        if A[0] == 0:
            return -1  # Can't move anywhere
        
        jumps = 0
        current_end = 0
        farthest = 0

        for i in range(n - 1):  # We don't need to jump from last index
            farthest = max(farthest, i + A[i])
            
            # If we reached the end of the range for the current jump
            if i == current_end:
                jumps += 1
                current_end = farthest
                
                if current_end >= n - 1:
                    return jumps
        
        return -1  # If loop finishes and we never reached last index

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
