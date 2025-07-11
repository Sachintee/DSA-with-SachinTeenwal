--- ❤️ ---

# 🚀 _Day 192. Itertools: Terminating Iterators_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/itertools-terminating-iterators/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
#include <numeric> // for accumulate
using namespace std;

int main() {
    vector<int> arr1 = {2, 1, 3, 4, 1};
    vector<int> arr2 = {1, 2, 4};
    vector<int> arr3 = {10, 3, 4, 3, 5, 6, 32, 11};

    // Creating arr4 by combining all three arrays
    vector<int> arr4;
    arr4.insert(arr4.end(), arr1.begin(), arr1.end());
    arr4.insert(arr4.end(), arr2.begin(), arr2.end());
    arr4.insert(arr4.end(), arr3.begin(), arr3.end());

    // Printing arr4
    for (int i : arr4)
        cout << i << " ";
    cout << endl;

    // Creating arr5 as successive multiplication (accumulate equivalent)
    vector<int> arr5;
    if (!arr4.empty()) {
        arr5.push_back(arr4[0]);
        for (size_t i = 1; i < arr4.size(); ++i) {
            arr5.push_back(arr5.back() * arr4[i]);
        }
    }

    // Printing arr5
    for (int i : arr5)
        cout << i << " ";
    cout << endl;

    return 0;
}

```

## Code (Java)

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        int[] arr1 = {2, 1, 3, 4, 1};
        int[] arr2 = {1, 2, 4};
        int[] arr3 = {10, 3, 4, 3, 5, 6, 32, 11};

        // Creating arr4 by combining all three arrays
        ArrayList<Integer> arr4 = new ArrayList<>();
        for (int i : arr1) arr4.add(i);
        for (int i : arr2) arr4.add(i);
        for (int i : arr3) arr4.add(i);

        // Printing arr4
        for (int i : arr4)
            System.out.print(i + " ");
        System.out.println();

        // Creating arr5 as successive multiplication
        ArrayList<Integer> arr5 = new ArrayList<>();
        if (!arr4.isEmpty()) {
            arr5.add(arr4.get(0));
            for (int i = 1; i < arr4.size(); i++) {
                arr5.add(arr5.get(i - 1) * arr4.get(i));
            }
        }

        // Printing arr5
        for (int i : arr5)
            System.out.print(i + " ");
        System.out.println();
    }
}

```

## Code (Python)

```python
import itertools
import operator

def main():
    arr1 = [2, 1, 3, 4, 1]
    arr2 = [1, 2, 4]
    arr3 = [10, 3, 4, 3, 5, 6, 32, 11]
    
    # make a new arr4 which include all the elements in order first of arr1 then arr2 and then arr3
    arr4 = list(itertools.chain(arr1, arr2, arr3))
    
    print(arr4)
    
    # using accumulate(), store the successive multiplication of elements of arr4 in a new list arr5
    arr5 = list(itertools.accumulate(arr4, operator.mul))
    
    print(arr5)
    
    return 0

if __name__ == '__main__':
    main()

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
