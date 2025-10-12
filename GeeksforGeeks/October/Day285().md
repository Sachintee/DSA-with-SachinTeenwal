--- ❤️ ---

# 🚀 _Day 285. MultiDimensional Arrays in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/multidimensional-arrays-in-c/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

void column_sum(int arr[1000][1000], int N, int M) {
    for (int j = 0; j < M; j++) {
        int sum = 0;
        for (int i = 0; i < N; i++) {
            sum += arr[i][j];
        }
        cout << sum << " ";
    }
}

int main() {
    int N, M;
    cin >> N >> M;
    int arr[1000][1000];
    
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < M; j++) {
            cin >> arr[i][j];
        }
    }
    
    column_sum(arr, N, M);
    return 0;
}

```

## Code (Java)

```java
import java.util.*;

public class Main {
    static void column_sum(int[][] arr) {
        int rows = arr.length;
        int cols = arr[0].length;

        for (int j = 0; j < cols; j++) {
            int sum = 0;
            for (int i = 0; i < rows; i++) {
                sum += arr[i][j];
            }
            System.out.print(sum + " ");
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();
        int M = sc.nextInt();

        int[][] arr = new int[N][M];
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < M; j++) {
                arr[i][j] = sc.nextInt();
            }
        }

        column_sum(arr);
    }
}

```

## Code (Python)

```python
def column_sum(arr):
    rows = len(arr)
    cols = len(arr[0])

    for j in range(cols):
        s = 0
        for i in range(rows):
            s += arr[i][j]
        print(s, end=" ")

# Input reading
N, M = map(int, input().split())
arr = [list(map(int, input().split())) for _ in range(N)]

column_sum(arr)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
