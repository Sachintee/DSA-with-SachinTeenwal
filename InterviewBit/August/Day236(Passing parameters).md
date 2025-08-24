--- ❤️ ---

# 🚀 _Day 236. Passing parameters_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/passing-parameters/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include<iostream>
using namespace std;

void compute(int &A, int &B, int &C) {
    A = A * A * A;
    B = B * B * B;
    C = C * C * C;
}

/*
int main()  {
    int A, B, C;
    cin>>A>>B>>C;
    compute(A, B, C);
    cout<<A<<endl;
    cout<<B<<endl;
    cout<<C<<endl;
    return 0;
}
*/
```

## Code (Java)

```java
import java.util.Scanner;

public class Solution {
    public static void compute(int[] A, int[] B, int[] C) {
        A[0] = A[0] * A[0] * A[0];
        B[0] = B[0] * B[0] * B[0];
        C[0] = C[0] * C[0] * C[0];
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int[] A = new int[1];
        int[] B = new int[1];
        int[] C = new int[1];
        A[0] = scanner.nextInt();
        B[0] = scanner.nextInt();
        C[0] = scanner.nextInt();
        compute(A, B, C);
        System.out.println(A[0]);
        System.out.println(B[0]);
        System.out.println(C[0]);
        scanner.close();
    }
}
```

## Code (Python)

```python
def compute(A, B, C):
    return A**3, B**3, C**3

def main():
    A = int(input())
    B = int(input())
    C = int(input())
    A, B, C = compute(A, B, C)
    print(A)
    print(B)
    print(C)

if __name__ == "__main__":
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
