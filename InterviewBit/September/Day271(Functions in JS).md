--- ❤️ ---

# 🚀 _Day 271. Functions in JS_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/functions-in-js/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

// Function to calculate product of three numbers
int myFunction(int a, int b, int c) {
    return a * b * c;
}

int main() {
    int a, b, c;
    cin >> a >> b >> c;
    
    int result = myFunction(a, b, c);
    cout << result << endl;
    
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;

public class Main {
    // Function to calculate product of three numbers
    public static int myFunction(int a, int b, int c) {
        return a * b * c;
    }
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int a = scanner.nextInt();
        int b = scanner.nextInt();
        int c = scanner.nextInt();
        
        int result = myFunction(a, b, c);
        System.out.println(result);
        
        scanner.close();
    }
}
```

## Code (Python)

```python
# Function to calculate product of three numbers
def myFunction(a, b, c):
    return a * b * c

# Reading input
a = int(input().strip())
b = int(input().strip())
c = int(input().strip())

# Calling function and printing result
result = myFunction(a, b, c)
print(result)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
