--- ❤️ ---

# 🚀 _Day 333. Count set bits_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/count-total-set-bits-1587115620/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    int countSetBits(int n) {
        if (n == 0) return 0;
        
        // find largest power of 2 <= n
        int x = 0;
        while ((1 << (x + 1)) <= n)
            x++;
        
        int p = 1 << x;  // 2^x
        
        // bits from 1 to (2^x - 1)
        int bits_upto_p = x * (p >> 1);
        
        // MSB bits from 2^x to n
        int msb_bits = n - p + 1;
        
        // recursive for remaining part
        int rest = countSetBits(n - p);
        
        return bits_upto_p + msb_bits + rest;
    }
};

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
