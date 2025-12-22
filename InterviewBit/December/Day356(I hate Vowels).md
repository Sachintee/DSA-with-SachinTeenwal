--- ❤️ ---

# 🚀 _Day 356. I hate Vowels_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/i-hate-vowels/)

## 🎯 **My Approach:**


## Code(SQL)
'''sql
SELECT Name
FROM Students
ORDER BY
    CASE
        WHEN LOWER(SUBSTR(Name, 1, 1)) IN ('a','e','i','o','u')
        THEN LEAST(Marks1, Marks2)
        ELSE GREATEST(Marks1, Marks2)
    END DESC;
'''

## Code(C++)
```cpp

```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
