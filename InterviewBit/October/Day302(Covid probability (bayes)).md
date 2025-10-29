--- ❤️ ---

# 🚀 _Day 302. Covid probability (bayes)_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/covid-probability-bayes/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

double solve(string A, string B, string C) {
    double P_Covid = stod(A);
    double P_Pos_given_Covid = stod(B);
    double P_Pos_given_NoCovid = stod(C);

    double numerator = P_Pos_given_Covid * P_Covid;
    double denominator = numerator + P_Pos_given_NoCovid * (1 - P_Covid);
    double result = numerator / denominator;

    return result;  // no rounding
}

int main() {
    string A, B, C;
    cin >> A >> B >> C;
    cout << fixed << setprecision(15) << solve(A, B, C);
    return 0;
}

```

## Code (Java)

```java
import java.util.*;

public class Main {
    public static double solve(String A, String B, String C) {
        double P_Covid = Double.parseDouble(A);
        double P_Pos_given_Covid = Double.parseDouble(B);
        double P_Pos_given_NoCovid = Double.parseDouble(C);

        double numerator = P_Pos_given_Covid * P_Covid;
        double denominator = numerator + P_Pos_given_NoCovid * (1 - P_Covid);
        double result = numerator / denominator;

        return result; // exact floating result
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String A = sc.next();
        String B = sc.next();
        String C = sc.next();
        System.out.println(solve(A, B, C));
    }
}

```

## Code (Python)

```python
def solve(A, B, C):
    # Convert inputs to float
    P_Covid = float(A)
    P_Pos_given_Covid = float(B)
    P_Pos_given_NoCovid = float(C)

    # Bayes' theorem
    numerator = P_Pos_given_Covid * P_Covid
    denominator = numerator + P_Pos_given_NoCovid * (1 - P_Covid)
    result = numerator / denominator

    # Return exact float value (no rounding)
    return result

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
