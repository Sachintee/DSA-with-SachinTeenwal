--- ❤️ ---

# 🚀 _Day 259. Replace Non-Coprime Numbers in Array_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/replace-non-coprime-numbers-in-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> replaceNonCoprimes(vector<int>& nums) {
        vector<int> stk;
        for (int x : nums) {
            stk.push_back(x);
            while (stk.size() > 1) {
                x = stk.back();
                int y = stk[stk.size() - 2];
                int g = __gcd(x, y);
                if (g == 1) {
                    break;
                }
                stk.pop_back();
                stk.back() = 1LL * x * y / g;
            }
        }
        return stk;
    }
};
```

## Code (Java)

```java
class Solution {
    public List<Integer> replaceNonCoprimes(int[] nums) {
        List<Integer> stk = new ArrayList<>();
        for (int x : nums) {
            stk.add(x);
            while (stk.size() > 1) {
                x = stk.get(stk.size() - 1);
                int y = stk.get(stk.size() - 2);
                int g = gcd(x, y);
                if (g == 1) {
                    break;
                }
                stk.remove(stk.size() - 1);
                stk.set(stk.size() - 1, (int) ((long) x * y / g));
            }
        }
        return stk;
    }

    private int gcd(int a, int b) {
        if (b == 0) {
            return a;
        }
        return gcd(b, a % b);
    }
}
```

## Code (Python)

```python
class Solution:
    def replaceNonCoprimes(self, nums: List[int]) -> List[int]:
        stk = []
        for x in nums:
            stk.append(x)
            while len(stk) > 1:
                x, y = stk[-2:]
                g = gcd(x, y)
                if g == 1:
                    break
                stk.pop()
                stk[-1] = x * y // g
        return stk
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
