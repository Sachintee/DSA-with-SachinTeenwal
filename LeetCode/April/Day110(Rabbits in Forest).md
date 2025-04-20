--- ❤️ ---

# 🚀 _Day 110. Rabbits in Forest_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/rabbits-in-forest/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int numRabbits(vector<int>& answers) {
        unordered_map<int, int> cnt;
        for (int x : answers) {
            ++cnt[x];
        }
        int ans = 0;
        for (auto& [x, v] : cnt) {
            int group = x + 1;
            ans += (v + group - 1) / group * group;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int numRabbits(int[] answers) {
        Map<Integer, Integer> cnt = new HashMap<>();
        for (int x : answers) {
            cnt.merge(x, 1, Integer::sum);
        }
        int ans = 0;
        for (var e : cnt.entrySet()) {
            int group = e.getKey() + 1;
            ans += (e.getValue() + group - 1) / group * group;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def numRabbits(self, answers: List[int]) -> int:
        cnt = Counter(answers)
        ans = 0
        for x, v in cnt.items():
            group = x + 1
            ans += (v + group - 1) // group * group
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
