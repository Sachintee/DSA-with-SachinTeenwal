--- ❤️ ---

# 🚀 _Day 324. Palindrome Numbers_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/palindrome-numbers/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    bool ispal(int x) {
        string s = to_string(x);
        int i = 0, j = s.size() - 1;
        while (i < j) {
            if (s[i] != s[j]) return false;
            i++; j--;
        }
        return true;
    }

    int solve(int A, int B, int C) {
        vector<int> pals;

        // collect palindromes
        for (int x = A; x <= B; x++) {
            if (ispal(x)) pals.push_back(x);
        }

        if (pals.empty()) return 0;

        // sliding window
        int n = pals.size();
        int i = 0, ans = 1;

        for (int j = 0; j < n; j++) {
            while (pals[j] - pals[i] > C) {
                i++;
            }
            ans = max(ans, j - i + 1);
        }

        return ans;
    }
};

```

## Code (Java)

```java
public class Solution {
    boolean isPal(int x) {
        String s = Integer.toString(x);
        int i = 0, j = s.length() - 1;
        while (i < j) {
            if (s.charAt(i) != s.charAt(j)) return false;
            i++; j--;
        }
        return true;
    }

    public int solve(int A, int B, int C) {
        java.util.ArrayList<Integer> pals = new java.util.ArrayList<>();

        // collect palindromes
        for (int x = A; x <= B; x++) {
            if (isPal(x)) pals.add(x);
        }

        if (pals.size() == 0) return 0;

        // sliding window
        int n = pals.size();
        int i = 0, ans = 1;

        for (int j = 0; j < n; j++) {
            while (pals.get(j) - pals.get(i) > C) {
                i++;
            }
            ans = Math.max(ans, j - i + 1);
        }

        return ans;
    }
}

```

## Code (Python)

```python
class Solution:
    def solve(self, A, B, C):
        # Function to check palindrome
        def ispal(x):
            s = str(x)
            return s == s[::-1]

        # Step 1: collect all palindromic integers
        pals = []
        for x in range(A, B + 1):
            if ispal(x):
                pals.append(x)

        # If no palindromes (rare), answer = 0
        if not pals:
            return 0

        # Step 2: Sliding window to find max count where max - min <= C
        n = len(pals)
        i = 0
        ans = 1

        for j in range(n):
            # shrink from left until condition satisfied
            while pals[j] - pals[i] > C:
                i += 1
            ans = max(ans, j - i + 1)

        return ans

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
