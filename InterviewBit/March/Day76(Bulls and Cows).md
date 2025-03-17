--- ❤️ ---

# 🚀 _Day 76. Bulls and Cows_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/bulls-and-cows/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

class Solution {
public:
    string solve(string secret, string guess) {
        int bulls = 0;
        int cows = 0;
        vector<int> secret_count(10, 0);
        vector<int> guess_count(10, 0);
        
        // Count bulls and populate counts for secret and guess
        for (int i = 0; i < secret.length(); i++) {
            if (secret[i] == guess[i]) {
                bulls++;
            } else {
                secret_count[secret[i] - '0']++;
                guess_count[guess[i] - '0']++;
            }
        }
        
        // Count cows
        for (int i = 0; i < 10; i++) {
            cows += min(secret_count[i], guess_count[i]);
        }
        
        return to_string(bulls) + "A" + to_string(cows) + "B";
    }
};
```

## Code (Java)

```java
public class Solution {
    public String solve(String secret, String guess) {
        int bulls = 0;
        int cows = 0;
        int[] secret_count = new int[10];
        int[] guess_count = new int[10];
        
        // Count bulls and populate counts for secret and guess
        for (int i = 0; i < secret.length(); i++) {
            if (secret.charAt(i) == guess.charAt(i)) {
                bulls++;
            } else {
                secret_count[secret.charAt(i) - '0']++;
                guess_count[guess.charAt(i) - '0']++;
            }
        }
        
        // Count cows
        for (int i = 0; i < 10; i++) {
            cows += Math.min(secret_count[i], guess_count[i]);
        }
        
        return bulls + "A" + cows + "B";
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, secret, guess):
        bulls = 0
        cows = 0
        secret_count = [0] * 10
        guess_count = [0] * 10
        
        # Count bulls and populate counts for secret and guess
        for i in range(len(secret)):
            if secret[i] == guess[i]:
                bulls += 1
            else:
                secret_count[int(secret[i])] += 1
                guess_count[int(guess[i])] += 1
        
        # Count cows
        for i in range(10):
            cows += min(secret_count[i], guess_count[i])
        
        return f"{bulls}A{cows}B"
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
