--- ❤️ ---

# 🚀 _Day 68. Single Number_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/single-number/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int singleNumber(vector<int>& A) {
        int result = 0;
        for (int num : A) {
            result ^= num;
        }
        return result;
    }
};
```

## Code (Java)

```java
class Solution {
    public int singleNumber(int[] A) {
        int result = 0;
        for (int num : A) {
            result ^= num;
        }
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    def singleNumber(self, A):
        result = 0
        for num in A:
            result ^= num
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
