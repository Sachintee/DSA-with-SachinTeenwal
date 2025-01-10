---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - two-pointer-algorithm
  - sliding-window
  - Hash
---

# 🚀 _Day 10. Count Distinct Elements in Every Window_ 🧠

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/two-pointer-technique-gfg-160/problem/count-distinct-elements-in-every-window)

## 💡 **Problem Description:**

Given an integer array `arr[]` and a number `k`, find the count of distinct elements in every window of size `k` in the array.

## 🔍 **Example Walkthrough:**

**Input:**  
`arr[] = [1, 2, 1, 3, 4, 2, 3], k = 4`  
**Output:**  
`[3, 4, 4, 3]`  

**Explanation:**  
- Window 1: `[1, 2, 1, 3]` → 3 distinct elements (`1, 2, 3`)  
- Window 2: `[2, 1, 3, 4]` → 4 distinct elements (`1, 2, 3, 4`)  
- Window 3: `[1, 3, 4, 2]` → 4 distinct elements (`1, 2, 3, 4`)  
- Window 4: `[3, 4, 2, 3]` → 3 distinct elements (`2, 3, 4`)  



**Input:**  
`arr[] = [4, 1, 1], k = 2`  
**Output:**  
`[2, 1]`  

**Explanation:**  
- Window 1: `[4, 1]` → 2 distinct elements (`4, 1`)  
- Window 2: `[1, 1]` → 1 distinct element (`1`)  



**Input:**  
`arr[] = [1, 1, 1, 1, 1], k = 3`  
**Output:**  
`[1, 1, 1]`  

**Explanation:**  
- Each window has only `1` distinct element (`1`) as all values in `arr` are identical.  



### **Constraints**

- $\( 1 \leq k \leq \text{arr.size()} \leq 10^5 \) $ 
- $\( 1 \leq \text{arr}[i] \leq 10^5 \) $



## 🎯 **My Approach:**

1. **Sliding Window with Frequency Map:**  
   - Use an unordered map (or dictionary) to keep track of the frequency of elements in the current window.  
   - Iterate over the array while maintaining the size of the window as `k`.  

2. **Steps:**  
   - Add the current element to the frequency map and increment its count.  
   - If the current index exceeds `k - 1`, count the distinct elements by checking the size of the map.  
   - Remove the element that is sliding out of the window by decrementing its count. If its count becomes `0`, remove it from the map.  

3. **Edge Cases:**  
   - If $\( k = 1 \)$, each element is its own window, so the count of distinct elements is $\( n \)$.  
   - If $\( n \leq k \)$, handle the window size appropriately without exceeding bounds.  



## 🕒 **Time and Auxiliary Space Complexity** 

**Expected Time Complexity:** $\( O(n) \)$, where $\( n \)$ is the size of the array. Each element is added to and removed from the map at most once.  

**Expected Auxiliary Space Complexity:** $\( O(n) \)$, as the size of the frequency map is proportional to the size of the window.  

## 📝 **Solution Code**

## Code (C++)

```cpp
#include <iostream>
#include <vector>
#include <unordered_map>
using namespace std;

class Solution {
public:
    vector<int> countDistinct(vector<int>& arr, int k) {
        int n = arr.size();
        vector<int> res;
        unordered_map<int, int> freq;

        for (int i = 0; i < k; i++) {
            freq[arr[i]]++;
        }
        res.push_back(freq.size());

        for (int i = k; i < n; i++) {
            freq[arr[i]]++;
            freq[arr[i - k]]--;

            if (freq[arr[i - k]] == 0) {
                freq.erase(arr[i - k]);
            }

            res.push_back(freq.size());
        }

        return res;
    }
};

int main() {
    Solution sol;

    vector<int> arr1 = {1, 2, 1, 3, 4, 2, 3};
    int k1 = 4;
    vector<int> result1 = sol.countDistinct(arr1, k1);
    for (int x : result1) {
        cout << x << " ";
    }
    cout << endl;

    vector<int> arr2 = {4, 1, 1};
    int k2 = 2;
    vector<int> result2 = sol.countDistinct(arr2, k2);
    for (int x : result2) {
        cout << x << " ";
    }
    cout << endl;

    return 0;
}

```


## Code (Java)

```java
import java.util.*;

class Solution {
    public List<Integer> countDistinct(int[] arr, int k) {
        int n = arr.length;
        List<Integer> res = new ArrayList<>();
        Map<Integer, Integer> freq = new HashMap<>();

        for (int i = 0; i < k; i++) {
            freq.put(arr[i], freq.getOrDefault(arr[i], 0) + 1);
        }
        res.add(freq.size());

        for (int i = k; i < n; i++) {
            freq.put(arr[i], freq.getOrDefault(arr[i], 0) + 1);

            int elementToRemove = arr[i - k];
            freq.put(elementToRemove, freq.get(elementToRemove) - 1);

            if (freq.get(elementToRemove) == 0) {
                freq.remove(elementToRemove);
            }

            res.add(freq.size());
        }

        return res;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        int[] arr1 = {1, 2, 1, 3, 4, 2, 3};
        int k1 = 4;
        System.out.println(sol.countDistinct(arr1, k1)); // Output: [3, 4, 4, 3]

        int[] arr2 = {4, 1, 1};
        int k2 = 2;
        System.out.println(sol.countDistinct(arr2, k2)); // Output: [2, 1]
    }
}
```


## Code (Python)

```python
class Solution:
    def countDistinct(self, arr, k):
        n = len(arr)  
        res = []
        freq = defaultdict(int)
        for i in range(k):
            freq[arr[i]] += 1
        res.append(len(freq))
      
        for i in range(k, n):
            freq[arr[i]] += 1
            freq[arr[i - k]] -= 1
            if freq[arr[i - k]] == 0:
                del freq[arr[i - k]]
          
            res.append(len(freq))
          
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
   <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>951</h4>
