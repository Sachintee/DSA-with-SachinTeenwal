---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Stack
---

# 🚀 _Day 54. Next Greater Element_ 🧠 

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/stack-gfg-160/problem/next-larger-element-1587115620)  

## 💡 **Problem Description:**  

Given an array `arr[]` of integers, the task is to find the **next greater element** for each element of the array in order of their appearance in the array.  
The **next greater element** of an element in the array is the **nearest element on the right** which is **greater than the current element**.  


## Code(C++)
```cpp
class Solution {
public:
    vector<int> nextLargerElement(vector<int>& arr) {
        stack<int> s;
        for (int i = arr.size() - 1; i >= 0; i--) {
            int val = arr[i];
            while (!s.empty() && s.top() <= val) s.pop();
            arr[i] = s.empty() ? -1 : s.top();
            s.push(val);
        }
        return arr;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> nextLargerElement(int[] arr) {
        Stack<Integer> s = new Stack<>();
        for (int i = arr.length - 1; i >= 0; i--) {
            int val = arr[i];
            while (!s.isEmpty() && s.peek() <= val) s.pop();
            arr[i] = s.isEmpty() ? -1 : s.peek();
            s.push(val);
        }
        ArrayList<Integer> res = new ArrayList<>();
        for (int num : arr) res.add(num);
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def nextLargerElement(self, arr):
        s = []
        for i in range(len(arr) - 1, -1, -1):
            val = arr[i]
            while s and s[-1] <= val:
                s.pop()
            arr[i] = -1 if not s else s[-1]
            s.append(val)
        return arr
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
