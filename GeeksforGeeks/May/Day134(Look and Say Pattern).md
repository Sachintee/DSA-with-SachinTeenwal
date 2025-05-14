# *134. Look and Say Pattern*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/decode-the-pattern1138/1)

## **🧩 Problem Description**

Given an integer `n`, return the `n`th term in the **Look-and-Say Sequence**, also known as the **Count and Say** sequence.

This sequence is built by describing the previous term in terms of the **count of digits in groups of the same digit**.


## Code(C++)
```cpp
class Solution {
  public:
    string countAndSay(int n) {
        string res = "1";
        for (int i = 1; i < n; ++i) {
            string temp;
            for (int j = 0; j < res.size(); ) {
                int k = j;
                while (k < res.size() && res[k] == res[j]) ++k;
                temp += to_string(k - j) + res[j];
                j = k;
            }
            res = temp;
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public String countAndSay(int n) {
        String result = "1";
        for (int i = 2; i <= n; i++) {
            StringBuilder temp = new StringBuilder();
            int count = 1;
            for (int j = 1; j < result.length(); j++) {
                if (result.charAt(j) == result.charAt(j - 1)) {
                    count++;
                } else {
                    temp.append(count).append(result.charAt(j - 1));
                    count = 1;
                }
            }
            temp.append(count).append(result.charAt(result.length() - 1));
            result = temp.toString();
        }
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    def countAndSay(self, n: int) -> str:
        result = "1"
        for _ in range(n - 1):
            i = 0
            new_result = ""
            while i < len(result):
                count = 1
                while i + 1 < len(result) and result[i] == result[i + 1]:
                    count += 1
                    i += 1
                new_result += str(count) + result[i]
                i += 1
            result = new_result
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
