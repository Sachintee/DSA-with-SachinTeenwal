--- ❤️ ---

# 🚀 _Day 304. Find Variance_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/find-variance/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    string solve(vector<int>& A) {
        int n = A.size();
        double mean = accumulate(A.begin(), A.end(), 0.0) / n;
        double variance = 0.0;

        for (int x : A) {
            variance += pow(x - mean, 2);
        }
        variance /= n;

        // Format to 2 decimal places
        stringstream ss;
        ss << fixed << setprecision(2) << variance;
        return ss.str();
    }
};

int main() {
    int n;
    cin >> n;
    vector<int> A(n);
    for (int i = 0; i < n; i++) cin >> A[i];

    Solution obj;
    cout << obj.solve(A);
    return 0;
}

```

## Code (Java)

```java
import java.util.*;
import java.text.DecimalFormat;

class Solution {
    public String solve(ArrayList<Integer> A) {
        int n = A.size();
        double sum = 0;
        for (int x : A) sum += x;

        double mean = sum / n;
        double variance = 0;

        for (int x : A) {
            variance += Math.pow(x - mean, 2);
        }
        variance /= n;

        DecimalFormat df = new DecimalFormat("0.00");
        return df.format(variance);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        ArrayList<Integer> A = new ArrayList<>();
        for (int i = 0; i < n; i++) {
            A.add(sc.nextInt());
        }

        Solution obj = new Solution();
        System.out.println(obj.solve(A));
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return a string
    def solve(self, A):
        n = len(A)
        mean = sum(A) / n
        variance = sum((x - mean) ** 2 for x in A) / n
        return f"{variance:.2f}"

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
