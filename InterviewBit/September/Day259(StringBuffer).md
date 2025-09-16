--- ❤️ ---

# 🚀 _Day 259. StringBuffer_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/stringbuffer/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
#include <algorithm>
using namespace std;

string solve(string s, int L, int R) {
    reverse(s.begin() + L, s.begin() + R + 1);
    return s;
}

int main() {
    string S;
    int L, R;
    
    getline(cin, S);
    cin >> L >> R;
    
    cout << solve(S, L, R) << endl;
    
    return 0;
}

```

## Code (Java)

```java
import java.lang.*;
import java.util.*;

public class Main {
    public static void main(String[] args) {
        //Don't alter anything here.
        Scanner inp = new Scanner(System.in);
        String S = inp.nextLine();
        int L = inp.nextInt();
        inp.nextLine();
        int R = inp.nextInt();
        inp.nextLine();
        inp.close();
        
        System.out.println(solve(S, L, R));
    }
    
    // Complete the function below
    public static String solve(String s, int L, int R) {
        StringBuffer sb = new StringBuffer(s);
        String substring = sb.substring(L, R + 1);  // Extract the substring
        String reversed = new StringBuffer(substring).reverse().toString();  // Reverse it
        sb.replace(L, R + 1, reversed);  // Replace the substring with its reversed version
        return sb.toString();
    }
}

```

## Code (Python)

```python
def solve(s, L, R):
    return s[:L] + s[L:R+1][::-1] + s[R+1:]

# Reading input
S = input()
L = int(input())
R = int(input())

# Output the result
print(solve(S, L, R))

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
