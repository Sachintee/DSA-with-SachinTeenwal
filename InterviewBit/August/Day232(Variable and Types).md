--- ❤️ ---

# 🚀 _Day 232. Variable and Types_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/variable-and-types/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include<iostream>
#include <iomanip> 
using namespace std;

int main() {
    int a;
    long b;
    char c;
    float d;
    double e;
    
    cin >> a >> b >> c >> d >> e;
    
    cout << a << endl;
    cout << b << endl;
    cout << c << endl;
    cout << fixed << setprecision(3) << d << endl;
    cout << fixed << setprecision(9) << e << endl;
    
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        int a = scanner.nextInt();
        long b = scanner.nextLong();
        char c = scanner.next().charAt(0);
        float d = scanner.nextFloat();
        double e = scanner.nextDouble();
        
        System.out.println(a);
        System.out.println(b);
        System.out.println(c);
        System.out.printf("%.3f\n", d);
        System.out.printf("%.9f\n", e);
        
        scanner.close();
    }
}
```

## Code (Python)

```python
def main():
    data = input().split()
    a = int(data[0])
    b = int(data[1])
    c = data[2]
    d = float(data[3])
    e = float(data[4])
    
    print(a)
    print(b)
    print(c)
    print("{:.3f}".format(d))
    print("{:.9f}".format(e))

if __name__ == "__main__":
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
