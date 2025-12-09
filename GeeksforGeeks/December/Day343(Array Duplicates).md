--- ❤️ ---

# 🚀 _Day 343. Array Duplicates_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/find-duplicates-in-an-array/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> findDuplicates(vector<int>& arr) {
        vector<int> ans;

        for(int i = 0; i < arr.size(); i++){
            int idx = abs(arr[i]) - 1;

            if(arr[idx] < 0) {
                ans.push_back(abs(arr[i]));
            } 
            else {
                arr[idx] = -arr[idx];
            }
        }

        return ans;
    }
};

```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
