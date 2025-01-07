
---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - two-pointer-algorithm
  - Arrays
---

# 🚀 _Day 7. Pair with Given Sum in a Sorted Array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/two-pointer-technique-gfg-160/problem/pair-with-given-sum-in-a-sorted-array4940)

## 💡 **Problem Description:**

You are given a sorted array `arr[]` of size `n` and an integer `target`. Your task is to find the number of pairs `(i, j)` such that `arr[i] + arr[j] = target`, where `i` and `j` are distinct indices (`i ≠ j`).

## 🔍 **Example Walkthrough:**

**Input:**  
`arr[] = [-1, 1, 5, 5, 7], target = 6`  
**Output:**  
`3`  
**Explanation:**  
The pairs `(1, 5)`, `(1, 5)`, and `(-1, 7)` sum up to `6`.



**Input:**  
`arr[] = [1, 1, 1, 1], target = 2`  
**Output:**  
`6`  
**Explanation:**  
There are 6 pairs: `(1, 1), (1, 1), (1, 1), (1, 1), (1, 1), (1, 1)`.



**Input:**  
`arr[] = [-1, 10, 10, 12, 15], target = 125`  
**Output:**  
`0`  
**Explanation:**  
No such pairs exist.



### Constraints:
- $`2 <= arr.size() <= 10^5`$
- $`-10^5 <= arr[i] <= 10^5`$
- $`-10^5 <= target <= 10^5`$



## 🎯 **My Approach:**

1. **Efficient Pair Counting Using a Hash Map**:  
   - This approach leverages a hash map to store the frequency of elements as we traverse the array.
   - For each element `x` in the array, the complement required to form a pair is `target - x`.
   - We check if the complement exists in the hash map. If yes, the frequency of the complement contributes to the count of valid pairs.
   - Update the frequency of `x` in the hash map.

2. **Steps:**
   - Initialize an empty hash map `freq` to store the frequency of elements.
   - Traverse the array and for each element:
     - Check if the complement (`target - x`) exists in the hash map.
     - Add the frequency of the complement to the result.
     - Update the frequency of the current element in the hash map.
   - Return the total count of pairs.



## 🕒 **Time and Auxiliary Space Complexity** 

- **Expected Time Complexity:** O(n), where `n` is the size of the array. Each element is processed once, and hash map operations (insertions and lookups) take O(1) on average.
- **Expected Auxiliary Space Complexity:** O(n), as we store the frequency of up to `n` elements in the hash map.

## 📝 **Solution Code**


## Code (C++)

```cpp
#include <unordered_map>
#include <vector>
using namespace std;

class Solution {
public:
    int countPairs(vector<int>& arr, int target) {
        unordered_map<int, int> container;
        int counter = 0;

        for (int num : arr) {
            int req = target - num;

            if (container.find(req) != container.end()) {
                counter += container[req];
            }

            container[num]++;
        }

        return counter;
    }
};

// Example usage:
// int main() {
//     Solution sol;
//     vector<int> arr = {1, 5, 7, 1};
//     int target = 6;
//     cout << sol.countPairs(arr, target) << endl; // Output: 2
//     return 0;
// }

```



## Code (Java)

```java
import java.util.HashMap;

class Solution {
    public int countPairs(int[] arr, int target) {
        HashMap<Integer, Integer> container = new HashMap<>();
        int counter = 0;

        for (int num : arr) {
            int req = target - num;

            if (container.containsKey(req)) {
                counter += container.get(req);
            }

            container.put(num, container.getOrDefault(num, 0) + 1);
        }

        return counter;
    }

    // Example usage:
    public static void main(String[] args) {
        Solution sol = new Solution();
        int[] arr = {1, 5, 7, 1};
        int target = 6;
        System.out.println(sol.countPairs(arr, target)); // Output: 2
    }
}
```



## Code (Python)

```python
class Solution:
    def countPairs (self, arr, target) : 
        #Complete the function
        #use map
        container={}
        counter=0
        for i in arr:
            req=target-i
            if req in container:
                counter+=container.get(req,0)
            container[i]=container.get(i,0)+1
        return counter
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal). Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
   <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>741</h4>
