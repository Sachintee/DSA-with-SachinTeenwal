--- ❤️ ---

# 🚀 _Day 283. Variables and Types in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/variables-and-types-in-c/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    int intValue;
    long long longValue;  // long long for 64-bit integer
    char charValue;
    float floatValue;
    double doubleValue;
    
    // Read all values
    cin >> intValue;
    cin >> longValue;
    cin >> charValue;
    cin >> floatValue;
    cin >> doubleValue;
    
    // Print all values
    cout << intValue << endl;
    cout << longValue << endl;
    cout << charValue << endl;
    cout << floatValue << endl;
    cout << doubleValue << endl;
    
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // Read integer
        int intValue = scanner.nextInt();
        
        // Read long
        long longValue = scanner.nextLong();
        
        // Read char - need to read as string and take first character
        char charValue = scanner.next().charAt(0);
        
        // Read float
        float floatValue = scanner.nextFloat();
        
        // Read double
        double doubleValue = scanner.nextDouble();
        
        // Print all values
        System.out.println(intValue);
        System.out.println(longValue);
        System.out.println(charValue);
        System.out.println(floatValue);
        System.out.println(doubleValue);
        
        scanner.close();
    }
}
```

## Code (Python)

```python
# Read integer
int_value = int(input())

# Read long (Python 3 int handles large integers)
long_value = int(input())

# Read char (in Python, read as string and take first character)
char_value = input()[0]

# Read float
float_value = float(input())

# Read double (Python uses float for both float and double)
double_value = float(input())

# Print all values
print(int_value)
print(long_value)
print(char_value)
print(float_value)
print(double_value)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
