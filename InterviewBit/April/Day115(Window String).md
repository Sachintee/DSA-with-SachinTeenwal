--- ❤️ ---

# 🚀 _Day 115. Window String_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/window-string/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>
#include <unordered_map>
#include <climits>

using namespace std;

class Solution {
public:
    string minWindow(string A, string B) {
        if (A.empty() || B.empty()) return "";

        unordered_map<char, int> dict_B;
        for (char c : B) {
            dict_B[c]++;
        }

        int required = dict_B.size();
        int left = 0, right = 0;
        int formed = 0;
        unordered_map<char, int> window_counts;
        int min_len = INT_MAX;
        int start = 0;

        while (right < A.size()) {
            char c = A[right];
            window_counts[c]++;

            if (dict_B.count(c) && window_counts[c] == dict_B[c]) {
                formed++;
            }

            while (left <= right && formed == required) {
                if (right - left + 1 < min_len) {
                    min_len = right - left + 1;
                    start = left;
                }

                char left_char = A[left];
                window_counts[left_char]--;
                if (dict_B.count(left_char) && window_counts[left_char] < dict_B[left_char]) {
                    formed--;
                }
                left++;
            }
            right++;
        }

        return min_len == INT_MAX ? "" : A.substr(start, min_len);
    }
};
```

## Code (Java)

```java
import java.util.HashMap;
import java.util.Map;

public class Solution {
    public String minWindow(String A, String B) {
        if (A == null || B == null || A.length() == 0 || B.length() == 0) {
            return "";
        }

        Map<Character, Integer> dict_B = new HashMap<>();
        for (char c : B.toCharArray()) {
            dict_B.put(c, dict_B.getOrDefault(c, 0) + 1);
        }

        int required = dict_B.size();
        int left = 0, right = 0;
        int formed = 0;
        Map<Character, Integer> window_counts = new HashMap<>();
        int min_len = Integer.MAX_VALUE;
        int start = 0;

        while (right < A.length()) {
            char c = A.charAt(right);
            window_counts.put(c, window_counts.getOrDefault(c, 0) + 1);

            if (dict_B.containsKey(c) && window_counts.get(c).intValue() == dict_B.get(c).intValue()) {
                formed++;
            }

            while (left <= right && formed == required) {
                if (right - left + 1 < min_len) {
                    min_len = right - left + 1;
                    start = left;
                }

                char left_char = A.charAt(left);
                window_counts.put(left_char, window_counts.get(left_char) - 1);
                if (dict_B.containsKey(left_char) && window_counts.get(left_char) < dict_B.get(left_char)) {
                    formed--;
                }
                left++;
            }
            right++;
        }

        return min_len == Integer.MAX_VALUE ? "" : A.substring(start, start + min_len);
    }
}
```

## Code (Python)

```python
from collections import defaultdict

class Solution:
    # @param A : string
    # @param B : string
    # @return a strings
    def minWindow(self, A, B):
        if not A or not B:
            return ""
        
        dict_B = defaultdict(int)
        for char in B:
            dict_B[char] += 1
        
        required = len(dict_B)
        left, right = 0, 0
        formed = 0
        window_counts = defaultdict(int)
        ans = float('inf'), None, None  # (window length, left, right)
        
        while right < len(A):
            char = A[right]
            window_counts[char] += 1
            
            if char in dict_B and window_counts[char] == dict_B[char]:
                formed += 1
            
            while left <= right and formed == required:
                char = A[left]
                
                if right - left + 1 < ans[0]:
                    ans = (right - left + 1, left, right)
                
                window_counts[char] -= 1
                if char in dict_B and window_counts[char] < dict_B[char]:
                    formed -= 1
                
                left += 1
            
            right += 1
        
        return "" if ans[0] == float('inf') else A[ans[1]: ans[2] + 1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
