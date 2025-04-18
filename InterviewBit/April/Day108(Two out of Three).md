--- ❤️ ---

# 🚀 _Day 108. Two out of Three_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/two-out-of-three/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <set>
#include <algorithm>

using namespace std;

vector<int> solve(vector<int>& A, vector<int>& B, vector<int>& C) {
    set<int> setA(A.begin(), A.end());
    set<int> setB(B.begin(), B.end());
    set<int> setC(C.begin(), C.end());
    
    set<int> all_elements;
    all_elements.insert(setA.begin(), setA.end());
    all_elements.insert(setB.begin(), setB.end());
    all_elements.insert(setC.begin(), setC.end());
    
    vector<int> result;
    for (int num : all_elements) {
        int count = 0;
        if (setA.find(num) != setA.end()) count++;
        if (setB.find(num) != setB.end()) count++;
        if (setC.find(num) != setC.end()) count++;
        if (count >= 2) {
            result.push_back(num);
        }
    }
    
    sort(result.begin(), result.end());
    return result;
}
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public ArrayList<Integer> solve(ArrayList<Integer> A, ArrayList<Integer> B, ArrayList<Integer> C) {
        Set<Integer> setA = new HashSet<>(A);
        Set<Integer> setB = new HashSet<>(B);
        Set<Integer> setC = new HashSet<>(C);
        
        Set<Integer> allElements = new HashSet<>();
        allElements.addAll(setA);
        allElements.addAll(setB);
        allElements.addAll(setC);
        
        ArrayList<Integer> result = new ArrayList<>();
        for (int num : allElements) {
            int count = 0;
            if (setA.contains(num)) count++;
            if (setB.contains(num)) count++;
            if (setC.contains(num)) count++;
            if (count >= 2) {
                result.add(num);
            }
        }
        
        Collections.sort(result);
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @param B : list of integers
    # @param C : list of integers
    # @return a list of integers
    def solve(self, A, B, C):
        setA = set(A)
        setB = set(B)
        setC = set(C)
        
        # Collect all unique elements from the three arrays
        all_elements = setA.union(setB).union(setC)
        
        result = []
        for num in all_elements:
            count = 0
            if num in setA:
                count += 1
            if num in setB:
                count += 1
            if num in setC:
                count += 1
            if count >= 2:
                result.append(num)
        
        return sorted(result)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
