--- ❤️ ---

# 🚀 _Day 293. Final Value of Variable After Performing Operations_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/final-value-of-variable-after-performing-operations/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int finalValueAfterOperations(vector<string>& operations) {
        int ans = 0;
        for (auto& s : operations) {
            ans += s[1] == '+' ? 1 : -1;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int finalValueAfterOperations(String[] operations) {
        int ans = 0;
        for (var s : operations) {
            ans += (s.charAt(1) == '+' ? 1 : -1);
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def finalValueAfterOperations(self, operations: List[str]) -> int:
        return sum(1 if s[1] == '+' else -1 for s in operations)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
