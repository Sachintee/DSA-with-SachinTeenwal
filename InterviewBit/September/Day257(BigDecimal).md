--- ❤️ ---

# 🚀 _Day 257. BigDecimal_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/bigdecimal/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
#include <cstdlib>

using namespace std;

// Helper function to compare two numeric strings as decimals
bool compareNumericStrings(const string &a, const string &b) {
    // Convert strings to long double for precision comparison
    long double num1 = stold(a);
    long double num2 = stold(b);

    return num1 > num2;
}

int main() {
    int n;
    cin >> n;
    vector<string> s(n);

    for (int i = 0; i < n; i++) {
        cin >> s[i];
    }

    // Sort using custom comparator in descending order
    stable_sort(s.begin(), s.end(), compareNumericStrings);

    for (const string &num : s) {
        cout << num << endl;
    }

    return 0;
}

```

## Code (Java)

```java
import java.lang.*;
import java.util.*;
import java.math.BigDecimal;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        String[] s = new String[n];

        for (int i = 0; i < n; i++) {
            s[i] = sc.next();
        }
        sc.close();

        // Custom comparator: sort by numeric value in descending order
        Arrays.sort(s, new Comparator<String>() {
            public int compare(String a, String b) {
                BigDecimal bd1 = new BigDecimal(a);
                BigDecimal bd2 = new BigDecimal(b);

                // Descending order: larger numbers come first
                return bd2.compareTo(bd1);
            }
        });

        // Output
        for (int i = 0; i < n; i++) {
            System.out.println(s[i]);
        }
    }
}

```

## Code (Python)

```python
from decimal import Decimal

n = int(input())
s = [input() for _ in range(n)]

# Sort using Decimal for numeric comparison, descending order
s.sort(key=lambda x: Decimal(x), reverse=True)

# Output
for num in s:
    print(num)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
