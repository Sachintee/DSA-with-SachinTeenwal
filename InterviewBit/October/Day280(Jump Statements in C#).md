--- ❤️ ---

# 🚀 _Day 280. Jump Statements in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/jump-statements-in-c/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
// Method 1: Using while loop with continue
#include <iostream>
using namespace std;

int main() {
    int N;
    cin >> N;
    
    int i = 1;
    while (i <= N) {
        if (i % 2 == 0) {
            i++;
            continue;
        }
        cout << i << endl;
        i++;
    }
    return 0;
}

// Method 2: Using do-while with continue
#include <iostream>
using namespace std;

int main() {
    int N;
    cin >> N;
    
    int i = 1;
    do {
        if (i % 2 == 0) {
            i++;
            continue;
        }
        cout << i << endl;
        i++;
    } while (i <= N);
    return 0;
}
```

## Code (Java)

```java
// Method 1: Using while loop with continue
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        
        int i = 1;
        while (i <= N) {
            if (i % 2 == 0) {
                i++;
                continue;
            }
            System.out.println(i);
            i++;
        }
        scanner.close();
    }
}

// Method 2: Enhanced for loop (without continue)
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        
        for (int i = 1; i <= N; i += 2) {
            System.out.println(i);
        }
        scanner.close();
    }
}
```

## Code (Python)

```python
# Method 1: Using while loop with continue
N = int(input())
i = 1
while i <= N:
    if i % 2 == 0:
        i += 1
        continue
    print(i)
    i += 1

# Method 2: Using range step (without continue)
N = int(input())
for i in range(1, N + 1, 2):
    print(i)

# Method 3: Using list comprehension (without continue)
N = int(input())
[print(i) for i in range(1, N + 1) if i % 2 != 0]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
