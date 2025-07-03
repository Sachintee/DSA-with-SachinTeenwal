--- ❤️ ---

# 🚀 _Day 184. Conditions and If-Else_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/conditions-and-if-else/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    cin >> num;

    if (num >= 90) {
        cout << "A" << endl;
    } else if (num >= 80) {
        cout << "B" << endl;
    } else if (num >= 70) {
        cout << "C" << endl;
    } else if (num >= 60) {
        cout << "D" << endl;
    } else if (num >= 50) {
        cout << "E" << endl;
    } else {
        cout << "F" << endl;
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
        int num = scanner.nextInt();

        if (num >= 90) {
            System.out.println("A");
        } else if (num >= 80) {
            System.out.println("B");
        } else if (num >= 70) {
            System.out.println("C");
        } else if (num >= 60) {
            System.out.println("D");
        } else if (num >= 50) {
            System.out.println("E");
        } else {
            System.out.println("F");
        }

        scanner.close();
    }
}
```

## Code (Python)

```python
def main():
    num = int(input())
    if num >= 90:
        print("A")
    elif num >= 80:
        print("B")
    elif num >= 70:
        print("C")
    elif num >= 60:
        print("D")
    elif num >= 50:
        print("E")
    else:
        print("F")

if __name__ == '__main__':
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
