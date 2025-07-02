--- ❤️ ---

# 🚀 _Day 183. Arithmetic operators on Numbers_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/arithmetic-operators-on-numbers/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <cmath> // For pow function

using namespace std;

int main() {
    int A, B;
    cin >> A >> B;
    
    // Sum
    cout << A + B << endl;
    
    // Difference
    cout << A - B << endl;
    
    // Product
    cout << A * B << endl;
    
    // Integer Division
    cout << A / B << endl;
    
    // Float Division
    cout << fixed;
    cout.precision(6); // To match Python's float precision
    cout << (double)A / B << endl;
    
    // Remainder
    cout << A % B << endl;
    
    // Power
    cout << (long long)pow(A, B) << endl;
    
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int A = scanner.nextInt();
        int B = scanner.nextInt();
        
        // Sum
        System.out.println(A + B);
        
        // Difference
        System.out.println(A - B);
        
        // Product
        System.out.println(A * B);
        
        // Integer Division
        System.out.println(A / B);
        
        // Float Division
        System.out.printf("%.6f%n", (double)A / B);
        
        // Remainder
        System.out.println(A % B);
        
        // Power
        System.out.println((long)Math.pow(A, B));
        
        scanner.close();
    }
}
```

## Code (Python)

```python
def main():
    A = int(input())
    B = int(input())
    
    # Sum
    print(A + B)
    
    # Difference
    print(A - B)
    
    # Product
    print(A * B)
    
    # Integer Division
    print(A // B)
    
    # Float Division
    print(A / B)
    
    # Remainder (Modulo)
    print(A % B)
    
    # Power
    print(A ** B)

if __name__ == '__main__':
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
