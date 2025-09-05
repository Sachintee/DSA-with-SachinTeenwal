--- ❤️ ---

# 🚀 _Day 248. Buffered Reader_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/buffered-reader/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    int num1, num2;
    cin >> num1 >> num2;   // read two integers
    cout << num1 << " " << num2 << endl;  // print space-separated
    return 0;
}

```

## Code (Java)

```java
import java.lang.*;
import java.util.*;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class Main {
    public static void main(String[] args) throws IOException {
        
        // Create BufferedReader object
        BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));
        
        // Read first integer
        int num1 = Integer.parseInt(reader.readLine());
        
        // Read second integer
        int num2 = Integer.parseInt(reader.readLine());
        
        // Print both on a single line space-separated
        System.out.println(num1 + " " + num2);
    }
}

```

## Code (Python)

```python
# Read two integers from input (each on a new line)
num1 = int(input().strip())
num2 = int(input().strip())

# Print them space-separated
print(num1, num2)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
