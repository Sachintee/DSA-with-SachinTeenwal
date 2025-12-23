--- ❤️ ---

# 🚀 _Day 357. Class Average_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/class-average/)

## 🎯 **My Approach:**

## Code(SQL)
'''sql
SELECT 
    COUNT(*) AS A
FROM Students s
WHERE s.Marks > (SELECT AVG(Marks) FROM Students)
GROUP BY s.ClassId
ORDER BY s.ClassId;
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
