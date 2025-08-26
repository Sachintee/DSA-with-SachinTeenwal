--- ❤️ ---

# 🚀 _Day 237. StringStream_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/stringstream/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include<iostream>
#include<sstream>
using namespace std;

int main() {
    string A;
    getline(cin, A);   // read the full input line (with commas)

    stringstream ss(A);
    int num;
    char ch;

    while (ss >> num) {
        cout << num << endl;
        ss >> ch;  // read and discard comma
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
        String A = sc.nextLine(); // read the full line

        String[] nums = A.split(","); // split by comma

        for (String num : nums) {
            System.out.println(num);
        }
    }
}

```

## Code (Python3)

```python
A = input().strip()

# split string by comma and print each number
for num in A.split(","):
    print(num)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
