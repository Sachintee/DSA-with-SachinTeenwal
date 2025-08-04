--- ❤️ ---

# 🚀 _Day 216. Equal Average Partition_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/equal-average-partition/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> A;
    map<tuple<int, int, int>, vector<int>> memo;

    vector<int> findSubset(int i, int k, int target) {
        if (k == 0 && target == 0) return {};
        if (k == 0 || i >= A.size()) return {};

        auto key = make_tuple(i, k, target);
        if (memo.count(key)) return memo[key];

        // Include A[i]
        if (A[i] <= target) {
            vector<int> withCurr = findSubset(i + 1, k - 1, target - A[i]);
            if (!withCurr.empty() || (k - 1 == 0 && target - A[i] == 0)) {
                withCurr.insert(withCurr.begin(), A[i]);
                return memo[key] = withCurr;
            }
        }

        // Skip A[i]
        return memo[key] = findSubset(i + 1, k, target);
    }

    vector<vector<int>> avgset(vector<int> &input) {
        A = input;
        sort(A.begin(), A.end());
        int n = A.size();
        int totalSum = accumulate(A.begin(), A.end(), 0);

        for (int k = 1; k < n; ++k) {
            if ((totalSum * k) % n != 0) continue;

            int targetSum = (totalSum * k) / n;
            memo.clear();
            vector<int> subset = findSubset(0, k, targetSum);

            if (!subset.empty()) {
                vector<int> rest;
                multiset<int> ms(A.begin(), A.end());
                for (int x : subset) ms.erase(ms.find(x));
                for (int x : ms) rest.push_back(x);
                return {subset, rest};
            }
        }

        return {};
    }
};

```

## Code (Java)

```java
import java.util.*;

public class Solution {
    List<Integer> A;
    Map<String, List<Integer>> memo = new HashMap<>();

    private List<Integer> findSubset(int i, int k, int target) {
        if (k == 0 && target == 0) return new ArrayList<>();
        if (k == 0 || i == A.size()) return null;

        String key = i + "," + k + "," + target;
        if (memo.containsKey(key)) return memo.get(key);

        int curr = A.get(i);

        if (curr <= target) {
            List<Integer> withCurr = findSubset(i + 1, k - 1, target - curr);
            if (withCurr != null) {
                List<Integer> res = new ArrayList<>();
                res.add(curr);
                res.addAll(withCurr);
                memo.put(key, res);
                return res;
            }
        }

        List<Integer> withoutCurr = findSubset(i + 1, k, target);
        memo.put(key, withoutCurr);
        return withoutCurr;
    }

    public List<List<Integer>> avgset(List<Integer> input) {
        A = new ArrayList<>(input);
        Collections.sort(A);
        int n = A.size();
        int totalSum = 0;
        for (int x : A) totalSum += x;

        for (int k = 1; k < n; k++) {
            if ((totalSum * k) % n != 0) continue;

            int targetSum = (totalSum * k) / n;
            memo.clear();
            List<Integer> subset = findSubset(0, k, targetSum);

            if (subset != null) {
                List<Integer> rest = new ArrayList<>(A);
                for (int x : subset) rest.remove((Integer) x);
                List<List<Integer>> ans = new ArrayList<>();
                ans.add(subset);
                ans.add(rest);
                return ans;
            }
        }

        return new ArrayList<>();
    }
}

```

## Code (Python)

```python
class Solution:
    def avgset(self, A):
        A.sort()
        total_sum = sum(A)
        n = len(A)
        memo = {}

        def find_subset(i, k, target):
            if k == 0 and target == 0:
                return []
            if k == 0 or i == len(A):
                return None
            if (i, k, target) in memo:
                return memo[(i, k, target)]
            
            # Include A[i]
            if A[i] <= target:
                with_curr = find_subset(i + 1, k - 1, target - A[i])
                if with_curr is not None:
                    memo[(i, k, target)] = [A[i]] + with_curr
                    return memo[(i, k, target)]

            # Skip A[i]
            without_curr = find_subset(i + 1, k, target)
            memo[(i, k, target)] = without_curr
            return without_curr

        for k in range(1, n):
            if total_sum * k % n != 0:
                continue
            target = (total_sum * k) // n
            subset = find_subset(0, k, target)
            if subset is not None:
                subset_set = set(subset)
                rest = []
                temp = A[:]
                for x in subset:
                    temp.remove(x)
                return [subset, temp]
        return []

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
