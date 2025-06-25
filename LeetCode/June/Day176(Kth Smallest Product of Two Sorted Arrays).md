--- ❤️ ---

# 🚀 _Day 176. Kth Smallest Product of Two Sorted Arrays_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/kth-smallest-product-of-two-sorted-arrays/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long kthSmallestProduct(vector<int>& nums1, vector<int>& nums2, long long k) {
        int m = nums1.size(), n = nums2.size();
        int a = max(abs(nums1[0]), abs(nums1[m - 1]));
        int b = max(abs(nums2[0]), abs(nums2[n - 1]));
        long long r = 1LL * a * b;
        long long l = -r;
        auto count = [&](long long p) {
            long long cnt = 0;
            for (int x : nums1) {
                if (x > 0) {
                    int l = 0, r = n;
                    while (l < r) {
                        int mid = (l + r) >> 1;
                        if (1LL * x * nums2[mid] > p) {
                            r = mid;
                        } else {
                            l = mid + 1;
                        }
                    }
                    cnt += l;
                } else if (x < 0) {
                    int l = 0, r = n;
                    while (l < r) {
                        int mid = (l + r) >> 1;
                        if (1LL * x * nums2[mid] <= p) {
                            r = mid;
                        } else {
                            l = mid + 1;
                        }
                    }
                    cnt += n - l;
                } else if (p >= 0) {
                    cnt += n;
                }
            }
            return cnt;
        };
        while (l < r) {
            long long mid = (l + r) >> 1;
            if (count(mid) >= k) {
                r = mid;
            } else {
                l = mid + 1;
            }
        }
        return l;
    }
};
```

## Code (Java)

```java
class Solution {
    private int[] nums1;
    private int[] nums2;

    public long kthSmallestProduct(int[] nums1, int[] nums2, long k) {
        this.nums1 = nums1;
        this.nums2 = nums2;
        int m = nums1.length;
        int n = nums2.length;
        int a = Math.max(Math.abs(nums1[0]), Math.abs(nums1[m - 1]));
        int b = Math.max(Math.abs(nums2[0]), Math.abs(nums2[n - 1]));
        long r = (long) a * b;
        long l = (long) -a * b;
        while (l < r) {
            long mid = (l + r) >> 1;
            if (count(mid) >= k) {
                r = mid;
            } else {
                l = mid + 1;
            }
        }
        return l;
    }

    private long count(long p) {
        long cnt = 0;
        int n = nums2.length;
        for (int x : nums1) {
            if (x > 0) {
                int l = 0, r = n;
                while (l < r) {
                    int mid = (l + r) >> 1;
                    if ((long) x * nums2[mid] > p) {
                        r = mid;
                    } else {
                        l = mid + 1;
                    }
                }
                cnt += l;
            } else if (x < 0) {
                int l = 0, r = n;
                while (l < r) {
                    int mid = (l + r) >> 1;
                    if ((long) x * nums2[mid] <= p) {
                        r = mid;
                    } else {
                        l = mid + 1;
                    }
                }
                cnt += n - l;
            } else if (p >= 0) {
                cnt += n;
            }
        }
        return cnt;
    }
}
```

## Code (Python)

```python
class Solution:
    def kthSmallestProduct(self, nums1: List[int], nums2: List[int], k: int) -> int:
        def count(p: int) -> int:
            cnt = 0
            n = len(nums2)
            for x in nums1:
                if x > 0:
                    cnt += bisect_right(nums2, p / x)
                elif x < 0:
                    cnt += n - bisect_left(nums2, p / x)
                else:
                    cnt += n * int(p >= 0)
            return cnt

        mx = max(abs(nums1[0]), abs(nums1[-1])) * max(abs(nums2[0]), abs(nums2[-1]))
        return bisect_left(range(-mx, mx + 1), k, key=count) - mx
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
