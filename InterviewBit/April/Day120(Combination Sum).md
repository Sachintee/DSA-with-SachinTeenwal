--- ❤️ ---

# 🚀 _Day 120. Combination Sum_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/combination-sum/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    vector<vector<int>> combinationSum(vector<int>& candidates, int target) {
        sort(candidates.begin(), candidates.end());
        vector<vector<int>> result;
        vector<int> path;
        backtrack(candidates, target, 0, path, result);
        return result;
    }
    
private:
    void backtrack(vector<int>& candidates, int target, int start, vector<int>& path, vector<vector<int>>& result) {
        if (target == 0) {
            result.push_back(path);
            return;
        }
        for (int i = start; i < candidates.size(); ++i) {
            if (candidates[i] > target) {
                continue;
            }
            if (i > start && candidates[i] == candidates[i - 1]) {
                continue; // Skip duplicates
            }
            path.push_back(candidates[i]);
            backtrack(candidates, target - candidates[i], i, path, result);
            path.pop_back();
        }
    }
};
```

## Code (Java)

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

class Solution {
    public List<List<Integer>> combinationSum(int[] candidates, int target) {
        Arrays.sort(candidates);
        List<List<Integer>> result = new ArrayList<>();
        backtrack(candidates, target, 0, new ArrayList<>(), result);
        return result;
    }
    
    private void backtrack(int[] candidates, int target, int start, List<Integer> path, List<List<Integer>> result) {
        if (target == 0) {
            result.add(new ArrayList<>(path));
            return;
        }
        for (int i = start; i < candidates.length; ++i) {
            if (candidates[i] > target) {
                continue;
            }
            if (i > start && candidates[i] == candidates[i - 1]) {
                continue; // Skip duplicates
            }
            path.add(candidates[i]);
            backtrack(candidates, target - candidates[i], i, path, result);
            path.remove(path.size() - 1);
        }
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @param B : integer
    # @return a list of list of integers
    def combinationSum(self, A, B):
        A = sorted(list(set(A)))  # Remove duplicates and sort
        result = []
        self.backtrack(A, B, 0, [], result)
        return result
    
    def backtrack(self, A, target, start, path, result):
        if target == 0:
            result.append(path.copy())
            return
        for i in range(start, len(A)):
            if A[i] > target:
                continue
            path.append(A[i])
            self.backtrack(A, target - A[i], i, path, result)
            path.pop()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
