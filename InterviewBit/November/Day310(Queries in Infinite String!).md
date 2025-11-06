--- ❤️ ---

# 🚀 _Day 310. Queries in Infinite String!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/queries-in-infinite-string/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <unordered_set>
#include <algorithm>
#include <cmath>
using namespace std;

class Solution {
public:
    vector<int> solve(vector<vector<int>>& A) {
        unordered_set<int> vowels_indices = {0, 4, 8, 14, 20};
        
        auto total_upto = [](long long k) -> long long {
            return 26 * k * (k + 1) / 2;
        };
        
        auto count_vowels_upto = [&](long long pos) -> long long {
            if (pos == 0) return 0;
            
            // Binary search for k
            long long low = 1, high = 200000; // large enough
            while (low < high) {
                long long mid = (low + high) / 2;
                if (total_upto(mid) >= pos) {
                    high = mid;
                } else {
                    low = mid + 1;
                }
            }
            long long k = low;
            
            // vowels from iterations 1..k-1
            long long res = 5 * (k - 1) * k / 2;
            
            long long rem = pos - total_upto(k - 1);
            long long full_blocks = rem / k;
            long long extra = rem % k;
            
            // count vowels in full_blocks
            for (long long b = 0; b < full_blocks; b++) {
                if (vowels_indices.count(b)) {
                    res += k;
                }
            }
            // count vowels in partial block
            if (vowels_indices.count(full_blocks)) {
                res += extra;
            }
            return res;
        };
        
        vector<int> ans;
        for (auto& query : A) {
            int L = query[0], R = query[1];
            ans.push_back(count_vowels_upto(R) - count_vowels_upto(L - 1));
        }
        return ans;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    private static final Set<Integer> vowelsIndices = new HashSet<>(
        Arrays.asList(0, 4, 8, 14, 20)
    );
    
    public int[] solve(int[][] A) {
        List<Integer> ans = new ArrayList<>();
        for (int[] query : A) {
            int L = query[0], R = query[1];
            long count = countVowelsUpto(R) - countVowelsUpto(L - 1);
            ans.add((int) count);
        }
        return ans.stream().mapToInt(i -> i).toArray();
    }
    
    private long totalUpto(long k) {
        return 26 * k * (k + 1) / 2;
    }
    
    private long countVowelsUpto(long pos) {
        if (pos == 0) return 0;
        
        // Binary search for k
        long low = 1, high = 200000;
        while (low < high) {
            long mid = (low + high) / 2;
            if (totalUpto(mid) >= pos) {
                high = mid;
            } else {
                low = mid + 1;
            }
        }
        long k = low;
        
        // vowels from iterations 1..k-1
        long res = 5 * (k - 1) * k / 2;
        
        long rem = pos - totalUpto(k - 1);
        long fullBlocks = rem / k;
        long extra = rem % k;
        
        // count vowels in fullBlocks
        for (long b = 0; b < fullBlocks; b++) {
            if (vowelsIndices.contains((int) b)) {
                res += k;
            }
        }
        // count vowels in partial block
        if (vowelsIndices.contains((int) fullBlocks)) {
            res += extra;
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A):
        vowels_indices = {0, 4, 8, 14, 20}
        
        def total_upto(k):
            return 26 * k * (k + 1) // 2
        
        def count_vowels_upto(pos):
            if pos == 0:
                return 0
            # Binary search for k
            low, high = 1, int(2e5)  # large enough
            while low < high:
                mid = (low + high) // 2
                if total_upto(mid) >= pos:
                    high = mid
                else:
                    low = mid + 1
            k = low
            
            # vowels from iterations 1..k-1
            res = 5 * (k - 1) * k // 2
            
            rem = pos - total_upto(k - 1)
            full_blocks = rem // k
            extra = rem % k
            
            # count vowels in full_blocks
            for b in range(full_blocks):
                if b in vowels_indices:
                    res += k
            # count vowels in partial block
            if full_blocks in vowels_indices:
                res += extra
            return res
        
        ans = []
        for L, R in A:
            ans.append(count_vowels_upto(R) - count_vowels_upto(L - 1))
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
