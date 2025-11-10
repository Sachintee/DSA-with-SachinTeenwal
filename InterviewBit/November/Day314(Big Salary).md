--- ❤️ ---

# 🚀 _Day 314. Big Salary_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/big-salary/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    vector<int> dailyWage = {10, 5, 7, 10};
    vector<int> daysWorked = {3, 7, 5, 3};

    int n = dailyWage.size();
    vector<int> earnings(n);

    for (int i = 0; i < n; i++) {
        earnings[i] = dailyWage[i] * daysWorked[i];
    }

    int maxEarning = *max_element(earnings.begin(), earnings.end());
    int countMax = count(earnings.begin(), earnings.end(), maxEarning);

    cout << "A" << endl;
    cout << countMax << endl;

    return 0;
}

```

## Code (Java)

```java
import java.util.*;

public class BigSalary {
    public static void main(String[] args) {
        int[] dailyWage = {10, 5, 7, 10};
        int[] daysWorked = {3, 7, 5, 3};

        int n = dailyWage.length;
        int[] earnings = new int[n];

        for (int i = 0; i < n; i++) {
            earnings[i] = dailyWage[i] * daysWorked[i];
        }

        int maxEarning = Arrays.stream(earnings).max().getAsInt();
        long countMax = Arrays.stream(earnings).filter(e -> e == maxEarning).count();

        System.out.println("A");
        System.out.println(countMax);
    }
}

```

## Code (Python)

```python
def big_salary(daily_wage, days_worked):
    earnings = [d * w for d, w in zip(daily_wage, days_worked)]
    max_earning = max(earnings)
    count_max = earnings.count(max_earning)

    print("A")
    print(count_max)

# Example
daily_wage = [10, 5, 7, 10]
days_worked = [3, 7, 5, 3]
big_salary(daily_wage, days_worked)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
