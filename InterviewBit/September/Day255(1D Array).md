--- ❤️ ---

# 🚀 _Day 255. 1D Array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/1d-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    int N;
    cin >> N;
    
    long long arr[N];
    
    // Take input
    for (int i = 0; i < N; i++) {
        cin >> arr[i];
    }
    
    // Print in reverse
    for (int i = N - 1; i >= 0; i--) {
        cout << arr[i] << endl;
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
        Scanner inp = new Scanner(System.in);
        
        int N = inp.nextInt();
        int[] arr = new int[N];
        
        // Input array elements
        for (int i = 0; i < N; i++) {
            arr[i] = inp.nextInt();
        }
        inp.close();
        
        // Print array in reverse order
        for (int i = N - 1; i >= 0; i--) {
            System.out.println(arr[i]);
        }
    }
}

```

## Code (Python)

```python
# Input N
N = int(input())

# Input array elements
arr = []
for _ in range(N):
    arr.append(int(input()))

# Print in reverse
for i in range(N - 1, -1, -1):
    print(arr[i])

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
