--- ❤️ ---

# 🚀 _Day 305. Probability Distribution_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/probability-distribution/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <cmath>
#include <iomanip>
using namespace std;

double calculate_probability(double M, double V, double W) {
    // Calculate standard deviation from variance
    double std_dev = sqrt(V);
    
    // Calculate z-score
    double z = (W - M) / std_dev;
    
    // Calculate probability using error function
    // P(X > W) = 1 - P(X <= W) = 1 - Φ(z)
    // where Φ(z) = 0.5 * (1 + erf(z/√2))
    double probability = 0.5 * (1 - erf(z / sqrt(2.0)));
    
    // Round to 2 decimal places
    return round(probability * 100) / 100.0;
}

// Example usage
int main() {
    double M, V, W;
    cin >> M >> V >> W;
    double result = calculate_probability(M, V, W);
    cout << fixed << setprecision(2) << result << endl;
    return 0;
}
```

## Code (Java)

```java
public class Solution {
    public static double calculate_probability(double M, double V, double W) {
        // Calculate standard deviation from variance
        double std_dev = Math.sqrt(V);
        
        // Calculate z-score
        double z = (W - M) / std_dev;
        
        // Calculate probability using error function
        // P(X > W) = 1 - P(X <= W) = 1 - Φ(z)
        // where Φ(z) = 0.5 * (1 + erf(z/√2))
        double probability = 0.5 * (1 - erf(z / Math.sqrt(2.0)));
        
        // Round to 2 decimal places
        return Math.round(probability * 100) / 100.0;
    }
    
    // Error function implementation for Java (since Java doesn't have built-in erf)
    private static double erf(double x) {
        // Constants
        double a1 =  0.254829592;
        double a2 = -0.284496736;
        double a3 =  1.421413741;
        double a4 = -1.453152027;
        double a5 =  1.061405429;
        double p  =  0.3275911;
        
        // Save the sign of x
        int sign = (x < 0) ? -1 : 1;
        x = Math.abs(x);
        
        // A&S formula 7.1.26
        double t = 1.0 / (1.0 + p * x);
        double y = 1.0 - (((((a5 * t + a4) * t) + a3) * t + a2) * t + a1) * t * Math.exp(-x * x);
        
        return sign * y;
    }
    
    // Example usage
    public static void main(String[] args) {
        double M = 42.0;
        double V = 19.5;
        double W = 46.0;
        double result = calculate_probability(M, V, W);
        System.out.printf("%.2f\n", result); // Output: 0.18
    }
}
```

## Code (Python)

```python
import math

def calculate_probability(M, V, W):
    """
    Calculate probability that a paperweight weighs more than W grams
    in a normal distribution with mean M and variance V
    """
    # Standard deviation from variance
    std_dev = math.sqrt(V)
    
    # Calculate z-score
    z = (W - M) / std_dev
    
    # Calculate probability using error function (erf)
    # P(X > W) = 1 - P(X <= W) = 1 - Φ(z)
    # where Φ(z) is the CDF of standard normal distribution
    
    # Using error function: Φ(z) = 0.5 * (1 + erf(z/√2))
    probability = 0.5 * (1 - math.erf(z / math.sqrt(2)))
    
    return round(probability, 2)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
