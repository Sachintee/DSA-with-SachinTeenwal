# *121. Pascal Triangle*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/pascal-triangle0652/1)


## **🧩 Problem Description**

Given a positive integer `n`, return the `n`th row of Pascal's Triangle.  
Pascal's Triangle is a triangular array where each element is the sum of the two elements directly above it in the previous row. The `n`th row contains `n` elements indexed from 0 to `n-1`, and follows the binomial coefficient formula:  
&nbsp; &nbsp; **`row[k] = C(n-1, k)`**

<img src="https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif" >


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> nthRowOfPascalTriangle(int n) {
        vector<int> row(n);
        row[0]=1;
        for(int i=1;i<n;++i) row[i]=row[i-1]*(n-i)/i;
        return row;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> nthRowOfPascalTriangle(int n) {
        ArrayList<Integer> row=new ArrayList<>();
        long v=1;
        for(int i=0;i<n;++i){
            row.add((int)v);
            v=v*(n-1-i)/(i+1);
        }
        return row;
    }
}
```

## Code (Python)

```python
class Solution:
    def nthRowOfPascalTriangle(self, n):
        row, v = [], 1
        for i in range(n):
            row.append(v)
            v = v * (n-1-i) // (i+1)
        return row
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
