--- ❤️ ---

# 🚀 _Day 334. Meeting Point_ 🧠


The problem can be found at the following link: [Problem Link]()

## 🎯 **My Approach:**


## Code(C++)
```cpp

```

## Code (Java)

```java

```

## Code (Python)

```python
class Solution:
    def solve(self, A):
        # Initialize with large values
        min_x = float('inf')
        min_x_y = float('inf')
        
        min_y = float('inf')
        min_y_x = float('inf')
        
        # Traverse all points
        for x, y in A:
            # Your meeting point: minimum x, tie -> minimum y
            if x < min_x or (x == min_x and y < min_x_y):
                min_x = x
                min_x_y = y
            
            # Friend's meeting point: minimum y, tie -> minimum x
            if y < min_y or (y == min_y and x < min_y_x):
                min_y = y
                min_y_x = x
        
        # Manhattan distance
        return abs(min_x - min_y_x) + abs(min_x_y - min_y)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
