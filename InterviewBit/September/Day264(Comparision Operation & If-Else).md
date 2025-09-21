--- ❤️ ---

# 🚀 _Day 264. Comparision Operation & If-Else_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/js-comparision-operation-if-else/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    cin >> num;
    
    if (num >= 90) {
        cout << "A";
    } else if (num >= 80) {
        cout << "B";
    } else if (num >= 70) {
        cout << "C";
    } else if (num >= 60) {
        cout << "D";
    } else if (num >= 50) {
        cout << "E";
    } else {
        cout << "F";
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
num = int(input().strip())

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
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
