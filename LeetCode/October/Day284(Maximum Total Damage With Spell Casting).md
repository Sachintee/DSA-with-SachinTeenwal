--- ❤️ ---

# 🚀 _Day 284. Maximum Total Damage With Spell Casting_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-total-damage-with-spell-casting/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long maximumTotalDamage(vector<int>& power) {
        sort(power.begin(), power.end());
        this->power = power;
        n = power.size();
        f.resize(n);
        nxt.resize(n);
        for (int i = 0; i < n; ++i) {
            cnt[power[i]]++;
            nxt[i] = upper_bound(power.begin() + i + 1, power.end(), power[i] + 2) - power.begin();
        }
        return dfs(0);
    }

private:
    unordered_map<int, int> cnt;
    vector<long long> f;
    vector<int> power;
    vector<int> nxt;
    int n;

    long long dfs(int i) {
        if (i >= n) {
            return 0;
        }
        if (f[i]) {
            return f[i];
        }
        long long a = dfs(i + cnt[power[i]]);
        long long b = 1LL * power[i] * cnt[power[i]] + dfs(nxt[i]);
        return f[i] = max(a, b);
    }
};
```

## Code (Java)

```java
class Solution {
    private Long[] f;
    private int[] power;
    private Map<Integer, Integer> cnt;
    private int[] nxt;
    private int n;

    public long maximumTotalDamage(int[] power) {
        Arrays.sort(power);
        this.power = power;
        n = power.length;
        f = new Long[n];
        cnt = new HashMap<>(n);
        nxt = new int[n];
        for (int i = 0; i < n; ++i) {
            cnt.merge(power[i], 1, Integer::sum);
            int l = Arrays.binarySearch(power, power[i] + 3);
            l = l < 0 ? -l - 1 : l;
            nxt[i] = l;
        }
        return dfs(0);
    }

    private long dfs(int i) {
        if (i >= n) {
            return 0;
        }
        if (f[i] != null) {
            return f[i];
        }
        long a = dfs(i + cnt.get(power[i]));
        long b = 1L * power[i] * cnt.get(power[i]) + dfs(nxt[i]);
        return f[i] = Math.max(a, b);
    }
}
```

## Code (Python)

```python
class Solution:
    def maximumTotalDamage(self, power: List[int]) -> int:
        @cache
        def dfs(i: int) -> int:
            if i >= n:
                return 0
            a = dfs(i + cnt[power[i]])
            b = power[i] * cnt[power[i]] + dfs(nxt[i])
            return max(a, b)

        n = len(power)
        cnt = Counter(power)
        power.sort()
        nxt = [bisect_right(power, x + 2, lo=i + 1) for i, x in enumerate(power)]
        return dfs(0)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
