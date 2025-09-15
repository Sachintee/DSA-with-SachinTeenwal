--- ❤️ ---

# 🚀 _Day 258. Substring_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/substring/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string A;
    cin >> A;
    
    int L, R;
    cin >> L >> R;
    
    // substr(start, length): extract substring starting at L of length (R - L + 1)
    cout << A.substr(L, R - L + 1) << endl;
    
    return 0;
}

```

## Code (Java)

```java
import java.lang.*;
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner inp = new Scanner(System.in);
        String A = inp.nextLine();
        int L = inp.nextInt();
        int R = inp.nextInt();
        inp.close();
        
        // Extract substring from L to R (inclusive)
        // substring(start, end) in Java is [start, end)
        String result = A.substring(L, R + 1);
        
        System.out.println(result);
    }
}

```

## Code (Python)

```python
# Take inputs
A = input()
L, R = map(int, input().split())

# Print substring from L to R (inclusive)
print(A[L:R+1])

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
