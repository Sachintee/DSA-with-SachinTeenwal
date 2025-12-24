--- ❤️ ---

# 🚀 _Day 358. Job Offer_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/job-offer/)

## 🎯 **My Approach:**

## Code(SQL)
```sql
SELECT 
    CONCAT(s.Name, ',', j.Date) AS Offers
FROM Students s
JOIN Jobs j
    ON s.Id = j.Id
JOIN Departments d
    ON s.DepartmentId = d.DepartmentId
ORDER BY d.DepartmentName;
```

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
