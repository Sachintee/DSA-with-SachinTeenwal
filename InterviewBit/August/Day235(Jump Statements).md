--- ❤️ ---

# 🚀 _Day 235. Jump Statements_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/jump-statements/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include<iostream>
using namespace std;

int main() {
    int N;
    cin >> N;

    for (int i = 0; i < N; i++) {
        if (i % 2 == 0) {
            continue; // skip even numbers
        }
        cout << i << endl; // only odd numbers will be printed
    }

    return 0;
}

```

## Code (Java)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();

        for (int i = 0; i < N; i++) {
            if (i % 2 == 0) {
                continue; // skip even numbers
            }
            System.out.println(i);
        }
    }
}

```

## Code (Python3)

```python3
N = int(input())

for i in range(N):
    if i % 2 == 0:
        continue   # skip even numbers
    print(i)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
