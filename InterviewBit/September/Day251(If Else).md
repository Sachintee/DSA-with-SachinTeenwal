--- ❤️ ---

# 🚀 _Day 251. If Else_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/if-else/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    int M;
    cin >> M;

    if (M % 3 == 0 && M % 5 == 0) {
        cout << "Good Number" << endl;
    } else if (M % 3 == 0) {
        cout << "Bad Number" << endl;
    } else if (M % 5 == 0) {
        cout << "Poor Number" << endl;
    } else {
        cout << "-1" << endl;
    }

    return 0;
}

```

## Code (Java)

```java
import java.lang.*;
import java.util.*;

public class Main {
    public static void main(String[] args) {
        /***Don't change the code here***/
        Scanner inp  = new Scanner(System.in);
        int M = inp.nextInt();
        inp.close();
        /*********************************/
        
        /**Write your code here**/
        if (M % 3 == 0 && M % 5 == 0) {
            System.out.println("Good Number");
        } else if (M % 3 == 0) {
            System.out.println("Bad Number");
        } else if (M % 5 == 0) {
            System.out.println("Poor Number");
        } else {
            System.out.println("-1");
        }
    }
}

```

## Code (Python3)

```python
# Read input
M = int(input())

# Apply conditions
if M % 3 == 0 and M % 5 == 0:
    print("Good Number")
elif M % 3 == 0:
    print("Bad Number")
elif M % 5 == 0:
    print("Poor Number")
else:
    print("-1")

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
