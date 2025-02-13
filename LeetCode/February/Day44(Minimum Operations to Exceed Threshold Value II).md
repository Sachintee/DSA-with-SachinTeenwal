--- ❤️ ---

# 🚀 _Day 44. Minimum Operations to Exceed Threshold Value II_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-operations-to-exceed-threshold-value-ii/description/?envType=daily-question&envId=2025-02-13)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <queue>
#include <algorithm>

using namespace std;

class Solution {
public:
    int minOperations(vector<int>& nums, int k) {
        priority_queue<int, vector<int>, greater<int>> minHeap(nums.begin(), nums.end());
        int operations = 0;
        
        while (minHeap.top() < k) {
            if (minHeap.size() < 2) {
                break;  // Not enough elements to perform the operation
            }
            int x = minHeap.top(); minHeap.pop();  // Smallest element
            int y = minHeap.top(); minHeap.pop();  // Second smallest element
            int newNum = min(x, y) * 2 + max(x, y);
            minHeap.push(newNum);
            operations++;
        }
        
        return operations;
    }
};

// Example usage
int main() {
    Solution sol;
    vector<int> nums1 = {2, 11, 10, 1, 3};
    cout << sol.minOperations(nums1, 10) << endl;  // Output: 2
    vector<int> nums2 = {1, 1, 2, 4, 9};
    cout << sol.minOperations(nums2, 20) << endl;  // Output: 4
    return 0;
}
```

## Code (Java)

```java
import java.util.PriorityQueue;

class Solution {
    public int minOperations(int[] nums, int k) {
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        for (int num : nums) {
            minHeap.add(num);
        }
        int operations = 0;
        
        while (minHeap.peek() < k) {
            if (minHeap.size() < 2) {
                break;  // Not enough elements to perform the operation
            }
            int x = minHeap.poll();  // Smallest element
            int y = minHeap.poll();  // Second smallest element
            int newNum = Math.min(x, y) * 2 + Math.max(x, y);
            minHeap.add(newNum);
            operations++;
        }
        
        return operations;
    }

    // Example usage
    public static void main(String[] args) {
        Solution sol = new Solution();
        System.out.println(sol.minOperations(new int[]{2, 11, 10, 1, 3}, 10));  // Output: 2
        System.out.println(sol.minOperations(new int[]{1, 1, 2, 4, 9}, 20));    // Output: 4
    }
}
```

## Code (Python)

```python
import heapq

class Solution:
    def minOperations(self, nums, k):
        heapq.heapify(nums)  # Convert nums into a min-heap
        operations = 0
        
        while nums[0] < k:
            if len(nums) < 2:
                break  # Not enough elements to perform the operation
            x = heapq.heappop(nums)  # Smallest element
            y = heapq.heappop(nums)  # Second smallest element
            new_num = min(x, y) * 2 + max(x, y)
            heapq.heappush(nums, new_num)
            operations += 1
        
        return operations

# Example usage
sol = Solution()
print(sol.minOperations([2, 11, 10, 1, 3], 10))  # Output: 2
print(sol.minOperations([1, 1, 2, 4, 9], 20))    # Output: 4
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
