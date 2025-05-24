# *144. Sum of All Substrings of a Number*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/sum-of-all-substrings-of-a-number-1587115621/1)


## **🧩 Problem Description**

Given a string `s` representing an integer number, return the **sum of all possible substrings** of this string interpreted as integers.

Each substring is formed by selecting a continuous sequence of characters from the original string. You must return the **sum of all such substrings**.

💡 The number may contain **leading zeros** and the result will always fit in a **32-bit signed integer**.



## Code(C++)
```cpp
class Solution {
  public:
    int sumSubstrings(string &s) {
        long long res=0,f=0;
        for(int i=0;i<s.size();++i){
            f=f*10+(s[i]-'0')*(i+1);
            res+=f;
        }
        return (int)res;
    }
};
```

## Code (Java)

```java
class Solution {
    public static int sumSubstrings(String s) {
        long res=0,f=0;
        for(int i=0;i<s.length();++i){
            f=f*10+(s.charAt(i)-'0')*(i+1);
            res+=f;
        }
        return (int)res;
    }
}
```

## Code (Python)

```python
class Solution:
    def sumSubstrings(self,s):
        res=f=0
        for i,ch in enumerate(s):
            f=f*10+int(ch)*(i+1)
            res+=f
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
