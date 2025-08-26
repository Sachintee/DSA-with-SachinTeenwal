--- ❤️ ---

# 🚀 _Day 238. Pointers to Array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/pointers-to-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include<iostream>
using namespace std;

int main() {
    int N;
    cin >> N;

    int grid[N][N];  // 2D array on stack

    // Fill values based on position
    for(int i = 0; i < N; i++) {
        for(int j = 0; j < N; j++) {
            if(i == j)
                grid[i][j] = 0;
            else if(i > j)
                grid[i][j] = -1;
            else
                grid[i][j] = 1;
        }
    }

    // Print (don’t modify this part in problem)
    for(int i = 0; i < N; i++) {
        for(int j = 0; j < N; j++) {
            cout << grid[i][j] << " ";
        }
        cout << endl;
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
        int[][] grid = new int[N][N];

        // Fill values
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                if (i == j) {
                    grid[i][j] = 0;
                } else if (i > j) {
                    grid[i][j] = -1;
                } else {
                    grid[i][j] = 1;
                }
            }
        }

        // Print the grid
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                System.out.print(grid[i][j] + " ");
            }
            System.out.println();
        }
    }
}

```

## Code (Python3)

```python
N = int(input())

# Create 2D list (grid)
grid = [[0] * N for _ in range(N)]

# Fill values
for i in range(N):
    for j in range(N):
        if i == j:
            grid[i][j] = 0
        elif i > j:
            grid[i][j] = -1
        else:
            grid[i][j] = 1

# Print the grid
for row in grid:
    print(" ".join(map(str, row)))

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
