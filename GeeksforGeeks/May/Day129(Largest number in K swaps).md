# *129. Largest Number in K Swaps*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/largest-number-in-k-swaps-1587115620/1)

## **🧩 Problem Description**

Given a string `s` representing a positive integer and an integer `k`, you may perform at most `k` swap operations on the digits of `s`. Each swap exchanges two digits at different positions. Return the lexicographically largest number (as a string) achievable under these operations.


## Code(C++)
```cpp
class Solution {
  public:
    string ans;
    void solve(string &s, int k, int idx) {
        if (k == 0) return;
        char mx = *max_element(s.begin() + idx, s.end());
        if (mx != s[idx]) k--;
        for (int i = s.size() - 1; i >= idx; i--) {
            if (s[i] == mx) {
                swap(s[i], s[idx]);
                if (s > ans) ans = s;
                solve(s, k, idx + 1);
                swap(s[i], s[idx]);
            }
        }
    }
    string findMaximumNum(string& s, int k) {
        ans = s;
        solve(s, k, 0);
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    String ans;
    void r(char[] a, int k, int i) {
        if (k == 0 || i == a.length) return;
        char m = a[i];
        for (int j = i + 1; j < a.length; j++) if (a[j] > m) m = a[j];
        if (m != a[i]) {
            for (int j = a.length - 1; j >= i; j--) if (a[j] == m) {
                char t = a[i]; a[i] = a[j]; a[j] = t;
                String cur = new String(a);
                if (cur.compareTo(ans) > 0) ans = cur;
                r(a, k - 1, i + 1);
                a[j] = a[i]; a[i] = t;
            }
        } else r(a, k, i + 1);
    }
    public String findMaximumNum(String s, int k) {
        ans = s;
        r(s.toCharArray(), k, 0);
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def findMaximumNum(self, s, k):
        ans = [s]
        def r(a, k, i):
            if k == 0 or i == len(a): return
            m = max(a[i:])
            if m != a[i]:
                for j in range(len(a)-1, i-1, -1):
                    if a[j] == m:
                        a[i], a[j] = a[j], a[i]
                        cur = ''.join(a)
                        if cur > ans[0]: ans[0] = cur
                        r(a, k-1, i+1)
                        a[i], a[j] = a[j], a[i]
            else:
                r(a, k, i+1)
        r(list(s), k, 0)
        return ans[0]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
