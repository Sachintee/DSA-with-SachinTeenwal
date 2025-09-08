--- ❤️ ---

# 🚀 _Day 251. Convert Integer to the Sum of Two No-Zero Integers_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/convert-integer-to-the-sum-of-two-no-zero-integers/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> getNoZeroIntegers(int n) {
        for (int a = 1;; ++a) {
            int b = n - a;
            if ((to_string(a) + to_string(b)).find('0') == -1) {
                return {a, b};
            }
        }
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] getNoZeroIntegers(int n) {
        for (int a = 1;; ++a) {
            int b = n - a;
            if (!(a + "" + b).contains("0")) {
                return new int[] {a, b};
            }
        }
    }
}
```

## Code (Python)

```python
class Solution:
    def getNoZeroIntegers(self, n: int) -> List[int]:
        for a in range(1, n):
            b = n - a
            if "0" not in str(a) + str(b):
                return [a, b]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
