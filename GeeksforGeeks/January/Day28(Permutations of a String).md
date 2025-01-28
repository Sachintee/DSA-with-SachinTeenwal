---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Strings
  - Recursion
  - Backtracking
---

# 🚀 _Day 28. Permutations of a String_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/recursion-and-backtracking-gfg-160/problem/permutations-of-a-given-string2041)

## 💡 **Problem Description:**
Given a string s, which may contain duplicate characters, your task is to generate and return an array of all unique permutations of the string. You can return your answer in any order.
--- ❤️ ---

## Code(C++)
```cpp
#include <iostream>
#include <vector>
#include <set>
#include <algorithm>
using namespace std;

class Solution {
public:
    vector<string> findPermutation(string s) {
        set<string> uniquePermutations;
        sort(s.begin(), s.end()); // Sort to handle duplicates easily
        do {
            uniquePermutations.insert(s);
        } while (next_permutation(s.begin(), s.end()));
        
        return vector<string>(uniquePermutations.begin(), uniquePermutations.end());
    }
};

int main() {
    Solution solution;
    string s = "ABC";
    vector<string> result = solution.findPermutation(s);
    for (const string &perm : result) {
        cout << perm << endl;
    }
    return 0;
}

```

## Code (Java)

```java
import java.util.*;

class Solution {
    public List<String> findPermutation(String s) {
        Set<String> uniquePermutations = new HashSet<>();
        permute(s.toCharArray(), 0, uniquePermutations);
        return new ArrayList<>(uniquePermutations);
    }

    private void permute(char[] chars, int start, Set<String> result) {
        if (start == chars.length) {
            result.add(new String(chars));
            return;
        }
        for (int i = start; i < chars.length; i++) {
            swap(chars, start, i);
            permute(chars, start + 1, result);
            swap(chars, start, i); // Backtrack
        }
    }

    private void swap(char[] chars, int i, int j) {
        char temp = chars[i];
        chars[i] = chars[j];
        chars[j] = temp;
    }

    public static void main(String[] args) {
        Solution solution = new Solution();
        String s = "ABC";
        List<String> result = solution.findPermutation(s);
        for (String perm : result) {
            System.out.println(perm);
        }
    }
}

```

## Code (Python)

```python
from itertools import permutations
class Solution:
    def findPermutation(self, s):
        # Code here
        return list(set("".join(i) for i in permutations(s)))
        

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>793</h4>
