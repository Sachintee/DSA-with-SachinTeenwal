# *117. Multiply Two Strings*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/multiply-two-strings/1)

## **🧩 Problem Description**

Given two numbers as strings `s1` and `s2`, calculate their **product** without using built-in big integer libraries or converting the entire strings to integers directly.  
Handle cases like negative numbers and leading zeros properly.

You don't need to explicitly show the '+' sign for positive numbers.


## Code(C++)
```cpp
class Solution {
  public:
    string multiplyStrings(string num1, string num2) {
        int sign=1;
        if(num1[0]=='-') sign*=-1,num1=num1.substr(1);
        if(num2[0]=='-') sign*=-1,num2=num2.substr(1);
        int n=num1.size(),m=num2.size();
        if(n==0||m==0) return "0";
        vector<int> res(n+m,0);
        for(int i=n-1;i>=0;i--)
            for(int j=m-1;j>=0;j--)
                res[i+j+1]+=(num1[i]-'0')*(num2[j]-'0');
        for(int i=n+m-1;i>0;i--){
            res[i-1]+=res[i]/10;
            res[i]%=10;
        }
        string ans;
        int i=0;
        while(i<res.size()&&res[i]==0) i++;
        for(;i<res.size();i++) ans+=res[i]+'0';
        if(ans.empty()) return "0";
        return sign==-1?"-"+ans:ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public String multiplyStrings(String s1, String s2) {
        int sign = 1;
        if (s1.charAt(0) == '-') { sign = -sign; s1 = s1.substring(1); }
        if (s2.charAt(0) == '-') { sign = -sign; s2 = s2.substring(1); }
        if (s1.equals("0") || s2.equals("0")) return "0";
        int n = s1.length(), m = s2.length();
        int[] res = new int[n + m];
        for (int i = n - 1; i >= 0; i--)
            for (int j = m - 1; j >= 0; j--)
                res[i + j + 1] += (s1.charAt(i) - '0') * (s2.charAt(j) - '0');
        for (int i = n + m - 1; i > 0; i--) {
            res[i - 1] += res[i] / 10;
            res[i] %= 10;
        }
        int i = 0;
        while (i < res.length && res[i] == 0) i++;
        StringBuilder ans = new StringBuilder();
        for (; i < res.length; i++) ans.append(res[i]);
        return sign == -1 ? "-" + ans.toString() : ans.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def multiplyStrings(self, s1, s2):
        sign=-1 if (s1[0]=='-')^(s2[0]=='-') else 1
        if s1[0]=='-': s1=s1[1:]
        if s2[0]=='-': s2=s2[1:]
        s1=s1.lstrip('0'); s2=s2.lstrip('0')
        if not s1 or not s2: return "0"
        n,m=len(s1),len(s2); r=[0]*(n+m)
        for i in range(n-1,-1,-1):
            for j in range(m-1,-1,-1):
                r[i+j+1]+=int(s1[i])*int(s2[j])
        for i in range(n+m-1,0,-1):
            r[i-1]+=r[i]//10; r[i]%=10
        i=0
        while i<len(r) and r[i]==0: i+=1
        ans=''.join(str(x) for x in r[i:])
        return "-"+ans if sign<0 else ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
