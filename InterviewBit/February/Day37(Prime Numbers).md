--- ❤️ ---

# 🚀 _Day 37. Prime Numbers_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/prime-numbers/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    vector<int> sieve(int A) {
        vector<int> primes;
        if (A < 2) return primes;
        
        vector<bool> is_prime(A + 1, true);
        is_prime[0] = is_prime[1] = false;

        for (int i = 2; i * i <= A; i++) {
            if (is_prime[i]) {
                for (int j = i * i; j <= A; j += i) {
                    is_prime[j] = false;
                }
            }
        }
        
        for (int i = 2; i <= A; i++) {
            if (is_prime[i]) {
                primes.push_back(i);
            }
        }
        return primes;
    }
};

// Driver code
int main() {
    Solution obj;
    int A = 50; // Example input
    vector<int> primes = obj.sieve(A);
    
    for (int prime : primes) {
        cout << prime << " ";
    }
    return 0;
}

```

## Code (Java)

```java
import java.util.*;

class Solution {
    public List<Integer> sieve(int A) {
        List<Integer> primes = new ArrayList<>();
        if (A < 2) return primes;
        
        boolean[] is_prime = new boolean[A + 1];
        Arrays.fill(is_prime, true);
        is_prime[0] = is_prime[

```

## Code (Python)

```python
class Solution:
    def sieve(self, A):
        if A < 2:
            return []
        
        # Initialize a boolean array to mark primes
        is_prime = [True] * (A + 1)
        is_prime[0] = is_prime[1] = False
        
        for i in range(2, int(A**0.5) + 1):
            if is_prime[i]:
                for j in range(i * i, A + 1, i):
                    is_prime[j] = False
        
        # Collect all prime numbers
        primes = [i for i, val in enumerate(is_prime) if val]
        return primes
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
