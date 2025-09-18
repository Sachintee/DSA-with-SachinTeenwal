--- ❤️ ---

# 🚀 _Day 261. Currency Formatter_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/currency-formatter/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    double payment;
    cin >> payment;

    // US format
    std::locale us("en_US.UTF-8");
    std::ostringstream usStream;
    usStream.imbue(us);
    usStream << std::showbase << std::put_money(payment * 100);
    string usCurrency = usStream.str();

    // India format (manual, since locale not directly supported)
    std::ostringstream indiaStream;
    indiaStream << "Rs." << fixed << setprecision(2) << payment;
    string indiaCurrency = indiaStream.str();

    cout << "US: " << usCurrency << endl;
    cout << "India: " << indiaCurrency << endl;

    return 0;
}

```

## Code (Java)

```java
import java.lang.*;
import java.util.*;
import java.text.*;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double payment = scanner.nextDouble();
        scanner.close();
        
        // US Currency
        NumberFormat usFormat = NumberFormat.getCurrencyInstance(Locale.US);
        String us = usFormat.format(payment);
        
        // India Currency (custom locale, since Locale.INDIA does not exist)
        Locale indiaLocale = new Locale("en", "IN");
        NumberFormat indiaFormat = NumberFormat.getCurrencyInstance(indiaLocale);
        String india = indiaFormat.format(payment);
        
        // Output
        System.out.println("US: " + us);
        System.out.println("India: " + india);
    }
}

```

## Code (Python)

```python
import locale

# Read input
payment = float(input())

# US formatting
locale.setlocale(locale.LC_ALL, 'en_US.UTF-8')
us = locale.currency(payment, grouping=True)

# India formatting (manual, because en_IN may not exist everywhere)
india = f"Rs.{payment:,.2f}"

# Output
print("US:", us)
print("India:", india)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
