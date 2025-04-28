--- ❤️ ---

# 🚀 _Day 118. Subset_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/subset/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    vector<vector<int>> subsets(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        vector<vector<int>> res;
        vector<int> subset;
        backtrack(nums, subset, 0, res);
        return res;
    }
    
private:
    void backtrack(vector<int>& nums, vector<int>& subset, int start, vector<vector<int>>& res) {
        res.push_back(subset);
        for (int i = start; i < nums.size(); ++i) {
            subset.push_back(nums[i]);
            backtrack(nums, subset, i + 1, res);
            subset.pop_back();
        }
    }
};
```

## Code (Java)

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

class Solution {
    public List<List<Integer>> subsets(int[] nums) {
        List<List<Integer>> res = new ArrayList<>();
        List<Integer> subset = new ArrayList<>();
        Arrays.sort(nums);
        backtrack(nums, subset, 0, res);
        return res;
    }
    
    private void backtrack(int[] nums, List<Integer> subset, int start, List<List<Integer>> res) {
        res.add(new ArrayList<>(subset));
        for (int i = start; i < nums.length; ++i) {
            subset.add(nums[i]);
            backtrack(nums, subset, i + 1, res);
            subset.remove(subset.size() - 1);
        }
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return a list of list of integers
    def subsets(self, A):
        A.sort()
        res = []
        self.backtrack(A, [], 0, res)
        return res
    
    def backtrack(self, A, subset, start, res):
        res.append(subset.copy())
        for i in range(start, len(A)):
            subset.append(A[i])
            self.backtrack(A, subset, i + 1, res)
            subset.pop()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
