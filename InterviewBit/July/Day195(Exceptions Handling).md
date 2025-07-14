--- ❤️ ---

# 🚀 _Day 195. Exceptions Handling_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/exceptions-handling/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
#include <stdexcept>

using namespace std;

int main() {
    int T;
    cin >> T;
    cin.ignore(); // To ignore the newline after T
    for (int i = 0; i < T; ++i) {
        string a, b;
        cin >> a >> b;
        try {
            int a_int = stoi(a);
            int b_int = stoi(b);
            if (b_int == 0) {
                throw runtime_error("integer division or modulo by zero");
            }
            cout << a_int / b_int << endl;
        } catch (const invalid_argument& e) {
            cout << "Error Code: invalid literal for int() with base 10: '" << (a.find_first_not_of("0123456789") != string::npos ? a : b) << "'" << endl;
        } catch (const runtime_error& e) {
            cout << "Error Code: " << e.what() << endl;
        }
    }
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int T = scanner.nextInt();
        scanner.nextLine(); // Consume the newline after T
        for (int i = 0; i < T; i++) {
            String[] parts = scanner.nextLine().split(" ");
            String a = parts[0];
            String b = parts[1];
            try {
                int aInt = Integer.parseInt(a);
                int bInt = Integer.parseInt(b);
                if (bInt == 0) {
                    throw new ArithmeticException("integer division or modulo by zero");
                }
                System.out.println(aInt / bInt);
            } catch (NumberFormatException e) {
                System.out.println("Error Code: invalid literal for int() with base 10: '" + (a.matches("\\d+") ? b : a) + "'");
            } catch (ArithmeticException e) {
                System.out.println("Error Code: " + e.getMessage());
            }
        }
        scanner.close();
    }
}
```

## Code (Python)

```python
def main():
    T = int(input())
    for _ in range(T):
        a, b = input().split()
        try:
            a_int = int(a)
            b_int = int(b)
            print(a_int // b_int)
        except ZeroDivisionError as e:
            print(f"Error Code: {e}")
        except ValueError as e:
            print(f"Error Code: {e}")

if __name__ == '__main__':
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
