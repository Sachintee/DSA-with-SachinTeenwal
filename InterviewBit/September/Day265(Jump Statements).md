--- ❤️ ---

# 🚀 _Day 265. Jump Statements_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/js-jump-statements/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    int N;
    cin >> N;
    
    for (int i = 1; i < N; i++) {
        // Use continue to skip even numbers
        if (i % 2 == 0) {
            continue;
        }
        
        // Use break when i reaches or exceeds N
        if (i >= N) {
            break;
        }
        
        cout << i << endl;
    }
    
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        
        for (int i = 1; i < N; i++) {
            // Use continue to skip even numbers
            if (i % 2 == 0) {
                continue;
            }
            
            // Use break when i reaches or exceeds N
            if (i >= N) {
                break;
            }
            
            System.out.println(i);
        }
        
        scanner.close();
    }
}
```

## Code (Python)

```python
# Read input
N = int(input().strip())

for i in range(1, N):
    # Use continue to skip even numbers
    if i % 2 == 0:
        continue
    
    # Use break when i reaches or exceeds N
    if i >= N:
        break
    
    print(i)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
