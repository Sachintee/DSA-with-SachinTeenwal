--- ❤️ ---

# 🚀 _Day 327. Hypothesis Testing in Salary of Data Scientists_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/hypothesis-testing-in-salary-of-data-scientists/)

## 🎯 **My Approach:**


## Code(C++)
```cpp

```

## Code (Java)

```java

```

## Code (Python)

```python
import math
from scipy.stats import t

def solve(salary_lst, mu):
    n = len(salary_lst)
    mean = sum(salary_lst) / n
    variance = sum((x - mean) ** 2 for x in salary_lst) / (n - 1)
    sd = math.sqrt(variance)

    t_stat = (mean - mu) / (sd / math.sqrt(n))
    df = n - 1

    # Two-tailed p-value
    p_value = 2 * (1 - t.cdf(abs(t_stat), df))

    return p_value < 0.05

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
