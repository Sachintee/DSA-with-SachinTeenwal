--- ❤️ ---

# 🚀 _Day 132. Finding 3-Digit Even Numbers_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/finding-3-digit-even-numbers/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> findEvenNumbers(vector<int>& digits) {
        int cnt[10]{};
        for (int x : digits) {
            ++cnt[x];
        }
        vector<int> ans;
        for (int x = 100; x < 1000; x += 2) {
            int cnt1[10]{};
            for (int y = x; y; y /= 10) {
                ++cnt1[y % 10];
            }
            bool ok = true;
            for (int i = 0; i < 10 && ok; ++i) {
                ok = cnt[i] >= cnt1[i];
            }
            if (ok) {
                ans.push_back(x);
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] findEvenNumbers(int[] digits) {
        int[] cnt = new int[10];
        for (int x : digits) {
            ++cnt[x];
        }
        List<Integer> ans = new ArrayList<>();
        for (int x = 100; x < 1000; x += 2) {
            int[] cnt1 = new int[10];
            for (int y = x; y > 0; y /= 10) {
                ++cnt1[y % 10];
            }
            boolean ok = true;
            for (int i = 0; i < 10 && ok; ++i) {
                ok = cnt[i] >= cnt1[i];
            }
            if (ok) {
                ans.add(x);
            }
        }
        return ans.stream().mapToInt(i -> i).toArray();
    }
}
```

## Code (Python)

```python
class Solution:
    def findEvenNumbers(self, digits: List[int]) -> List[int]:
        cnt = Counter(digits)
        ans = []
        for x in range(100, 1000, 2):
            cnt1 = Counter()
            y = x
            while y:
                y, v = divmod(y, 10)
                cnt1[v] += 1
            if all(cnt[i] >= cnt1[i] for i in range(10)):
                ans.append(x)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
