--- ❤️ ---

# 🚀 _Day 190. Set operations_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/set-operations/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <set>
#include <vector>
#include <algorithm>

void printSet(const std::set<int>& s) {
    std::vector<int> li(s.begin(), s.end());
    std::sort(li.begin(), li.end());
    std::cout << "[";
    for (size_t i = 0; i < li.size(); ++i) {
        std::cout << li[i];
        if (i != li.size() - 1) {
            std::cout << ", ";
        }
    }
    std::cout << "]" << std::endl;
}

int main() {
    std::set<int> X = {1, 3, 7, 5, 6, 10, 20, 21, 22, 23, 55, 51, 2, 19, 9, 17, 27, 26, 25, 35};
    std::set<int> Y = {2, 10, 13, 18, 17, 22, 28, 27, 5, 49, 46, 43, 3};
    std::set<int> Z = {21, 1, 32, 25, 12, 11, 8, 10, 26, 16, 31, 20, 30, 14};

    // 'set1' contains the student who loves to play all three sports
    std::set<int> set1;
    std::set_intersection(X.begin(), X.end(), Y.begin(), Y.end(), std::inserter(set1, set1.begin()));
    std::set<int> temp;
    std::set_intersection(set1.begin(), set1.end(), Z.begin(), Z.end(), std::inserter(temp, temp.begin()));
    set1 = temp;

    printSet(set1);

    // 'set2' contains the student who loves to play both Football and Cricket, but don't play Basketball
    std::set<int> set2;
    std::set_intersection(X.begin(), X.end(), Y.begin(), Y.end(), std::inserter(set2, set2.begin()));
    std::set<int> temp2;
    std::set_difference(set2.begin(), set2.end(), Z.begin(), Z.end(), std::inserter(temp2, temp2.begin()));
    set2 = temp2;

    printSet(set2);

    // 'set3' contains the student who loves to play Cricket, but don't loves any other sport
    std::set<int> unionXZ;
    std::set_union(X.begin(), X.end(), Z.begin(), Z.end(), std::inserter(unionXZ, unionXZ.begin()));
    std::set<int> set3;
    std::set_difference(Y.begin(), Y.end(), unionXZ.begin(), unionXZ.end(), std::inserter(set3, set3.begin()));

    printSet(set3);

    return 0;
}
```

## Code (Java)

```java
import java.util.*;

public class Main {
    public static void printSet(Set<Integer> set) {
        List<Integer> li = new ArrayList<>(set);
        Collections.sort(li);
        System.out.println(li);
    }

    public static void main(String[] args) {
        Set<Integer> X = new HashSet<>(Arrays.asList(1, 3, 7, 5, 6, 10, 20, 21, 22, 23, 55, 51, 2, 19, 9, 17, 27, 26, 25, 35));
        Set<Integer> Y = new HashSet<>(Arrays.asList(2, 10, 13, 18, 17, 22, 28, 27, 5, 49, 46, 43, 3));
        Set<Integer> Z = new HashSet<>(Arrays.asList(21, 1, 32, 25, 12, 11, 8, 10, 26, 16, 31, 20, 30, 14));

        // 'set1' contains the student who loves to play all three sports
        Set<Integer> set1 = new HashSet<>(X);
        set1.retainAll(Y);
        set1.retainAll(Z);

        printSet(set1);

        // 'set2' contains the student who loves to play both Football and Cricket, but don't play Basketball
        Set<Integer> set2 = new HashSet<>(X);
        set2.retainAll(Y);
        set2.removeAll(Z);

        printSet(set2);

        // 'set3' contains the student who loves to play Cricket, but don't loves any other sport
        Set<Integer> unionXZ = new HashSet<>(X);
        unionXZ.addAll(Z);
        Set<Integer> set3 = new HashSet<>(Y);
        set3.removeAll(unionXZ);

        printSet(set3);
    }
}
```

## Code (Python)

```python
def printset(setx):
    li = list(setx)
    li.sort()
    print(li)

def main():
    # Below are the three sets 
    X = set([1, 3, 7, 5, 6, 10, 20, 21, 22, 23, 55, 51, 2, 19, 9, 17, 27, 26, 25, 35])
    Y = set([2, 10, 13, 18, 17, 22, 28, 27, 5, 49, 46, 43, 3])
    Z = set([21, 1, 32, 25, 12, 11, 8, 10, 26, 16, 31, 20, 30, 14])
    
    # 'set1' contains the student who loves to play all three sports
    set1 = X.intersection(Y).intersection(Z)
    
    printset(set1)
    
    # 'set2' contains the student who loves to play both Football and Cricket, but don't play Basketball
    set2 = X.intersection(Y).difference(Z)
    
    printset(set2)
    
    # 'set3' contains the student who loves to play Cricket, but don't loves any other sport
    set3 = Y.difference(X.union(Z))
    
    printset(set3)
    return 0

if __name__ == '__main__':
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
