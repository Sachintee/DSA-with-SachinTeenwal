--- ❤️ ---

# 🚀 _Day 140. Order of People Heights_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/order-of-people-heights/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
using namespace std;

class Solution {
public:
    vector<int> order(vector<int>& A, vector<int>& B) {
        vector<pair<int, int>> people;
        for (int i = 0; i < A.size(); ++i) {
            people.emplace_back(A[i], B[i]);
        }
        // Sort by height in descending order
        sort(people.begin(), people.end(), [](const pair<int, int>& a, const pair<int, int>& b) {
            return a.first > b.first;
        });
        
        vector<int> result;
        for (const auto& person : people) {
            result.insert(result.begin() + person.second, person.first);
        }
        return result;
    }
};
```

## Code (Java)

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;

public class Solution {
    public ArrayList<Integer> order(ArrayList<Integer> A, ArrayList<Integer> B) {
        List<Pair> people = new ArrayList<>();
        for (int i = 0; i < A.size(); i++) {
            people.add(new Pair(A.get(i), B.get(i)));
        }
        // Sort by height in descending order
        Collections.sort(people, new Comparator<Pair>() {
            @Override
            public int compare(Pair a, Pair b) {
                return b.height - a.height;
            }
        });
        
        ArrayList<Integer> result = new ArrayList<>();
        for (Pair person : people) {
            result.add(person.infront, person.height);
        }
        return result;
    }
    
    class Pair {
        int height;
        int infront;
        Pair(int height, int infront) {
            this.height = height;
            this.infront = infront;
        }
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @param B : list of integers
    # @return a list of integers
    def order(self, A, B):
        # Combine heights and infronts into a list of tuples and sort by height in descending order
        people = list(zip(A, B))
        people.sort(reverse=True, key=lambda x: x[0])
        
        result = []
        for height, infront in people:
            # Insert the current person at the 'infront' position in the result list
            result.insert(infront, height)
        
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
