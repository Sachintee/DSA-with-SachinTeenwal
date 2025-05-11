# *131. K-th Largest Sum Contiguous Subarray*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/k-th-largest-sum-contiguous-subarray/1)

## **🧩 Problem Description**

Given an array `arr[]` of size `n`, find the **sum of the K-th largest** sum among all possible contiguous subarrays of `arr`. In other words, list all contiguous subarray sums, sort them in descending order, and return the K-th element.


## Code(C++)
```cpp

class Solution {
  public:
    int kthLargest(vector<int> &arr, int k) {
        vector<int> p(arr.size() + 1);
        for (int i = 0; i < arr.size(); ++i) p[i + 1] = p[i] + arr[i];
        priority_queue<int, vector<int>, greater<int>> q;
        for (int i = 0; i < arr.size(); ++i)
            for (int j = i + 1; j <= arr.size(); ++j) {
                q.push(p[j] - p[i]);
                if (q.size() > k) q.pop();
            }
        return q.top();
    }
};
```

## Code (Java)

```java
class Solution {
    public static int kthLargest(int[] arr, int k) {
        int[] p = new int[arr.length + 1];
        for (int i = 0; i < arr.length; ++i) p[i + 1] = p[i] + arr[i];
        PriorityQueue<Integer> q = new PriorityQueue<>();
        for (int i = 0; i < arr.length; ++i)
            for (int j = i + 1; j <= arr.length; ++j) {
                q.add(p[j] - p[i]);
                if (q.size() > k) q.poll();
            }
        return q.peek();
    }
}
```

## Code (Python)

```python
class Solution:
    def kthLargest(self, arr, k) -> int:
        p = [0]
        for x in arr: p.append(p[-1] + x)
        q = []
        for i in range(len(arr)):
            for j in range(i + 1, len(arr) + 1):
                heapq.heappush(q, p[j] - p[i])
                if len(q) > k: heapq.heappop(q)
        return q[0]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
