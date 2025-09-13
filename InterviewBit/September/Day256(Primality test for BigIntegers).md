--- ❤️ ---

# 🚀 _Day 256. Primality test for BigIntegers_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/primality-test-for-bigintegers/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
#include <boost/multiprecision/cpp_int.hpp>

using namespace std;
using namespace boost::multiprecision;

bool isPrime(cpp_int n) {
    if (n <= 1)
        return false;
    if (n == 2 || n == 3)
        return true;
    if (n % 2 == 0)
        return false;

    for (cpp_int i = 3; i * i <= n; i += 2) {
        if (n % i == 0)
            return false;
    }
    return true;
}

int main() {
    string numStr;
    cin >> numStr;

    cpp_int n(numStr);

    if (isPrime(n)) {
        cout << "prime" << endl;
    } else {
        cout << "not prime" << endl;
    }

    return 0;
}

```

## Code (Java)

```java
import java.lang.*;
import java.util.*;
import java.math.BigInteger;

public class Main {
    public static void main(String[] args) {
        Scanner inp = new Scanner(System.in);
        String numStr = inp.nextLine();
        inp.close();

        // Create a BigInteger from the input string
        BigInteger n = new BigInteger(numStr);

        // Check primality using isProbablePrime with a certainty parameter
        if (n.isProbablePrime(10)) {
            System.out.println("prime");
        } else {
            System.out.println("not prime");
        }
    }
}

```

## Code (Python3)

```python
import sympy

# Read the input number as a string and convert it to int
n = int(input())

# Check if n is prime
if sympy.isprime(n):
    print("prime")
else:
    print("not prime")

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
