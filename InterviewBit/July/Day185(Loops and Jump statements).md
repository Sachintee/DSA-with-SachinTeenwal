--- ❤️ ---

# 🚀 _Day 185. Loops and Jump statements_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/loops-and-jump-statements/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    int N;
    cin >> N;
    
    for (int i = 0; i < N; i++) {
        if (i % 2 != 0) {
            cout << i << endl;
        }
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
        
        for (int i = 0; i < N; i++) {
            if (i % 2 != 0) {
                System.out.println(i);
            }
        }
        
        scanner.close();
    }
}
```

## Code (Python)

```python
def main():
    N = int(input())
    for i in range(N):
        if i % 2 != 0:
            print(i)

if __name__ == '__main__':
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
