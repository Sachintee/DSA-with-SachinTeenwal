--- ❤️ ---

# 🚀 _Day 313. Row-wise unique_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/row-wise-unique/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
using namespace std;

void countfreq(const vector<vector<int>>& arr2d) {
    vector<vector<int>> result;

    for (const auto& row : arr2d) {
        vector<int> freq(10, 0);  // For student IDs 1 to 10
        for (int val : row) {
            if (val >= 1 && val <= 10)
                freq[val - 1]++;
        }
        result.push_back(freq);
    }

    // Print 2D result list
    cout << "[";
    for (size_t i = 0; i < result.size(); ++i) {
        cout << "[";
        for (size_t j = 0; j < 10; ++j) {
            cout << result[i][j];
            if (j < 9) cout << ", ";
        }
        cout << "]";
        if (i < result.size() - 1) cout << ", ";
    }
    cout << "]" << endl;
}

int main() {
    vector<vector<int>> arr2d = {
        {1, 1, 2, 5, 7, 6, 7, 7, 6, 3},
        {8, 5, 4, 7, 5, 2, 6, 10, 1, 7},
        {4, 3, 10, 4, 4, 4, 3, 1, 4, 3},
        {1, 4, 1, 1, 8, 4, 9, 8, 5, 5},
        {1, 1, 4, 4, 2, 10, 5, 6, 8, 1}
    };

    countfreq(arr2d);
    return 0;
}

```

## Code (Java)

```java
import java.util.*;

public class CountFreq {
    public static void countfreq(List<List<Integer>> arr2d) {
        List<List<Integer>> result = new ArrayList<>();

        for (List<Integer> row : arr2d) {
            int[] freq = new int[10]; // For IDs 1–10
            for (int val : row) {
                if (val >= 1 && val <= 10)
                    freq[val - 1]++;
            }
            List<Integer> freqList = new ArrayList<>();
            for (int f : freq) freqList.add(f);
            result.add(freqList);
        }

        // Print 2D list
        System.out.print("[");
        for (int i = 0; i < result.size(); i++) {
            System.out.print(result.get(i));
            if (i < result.size() - 1) System.out.print(", ");
        }
        System.out.println("]");
    }

    public static void main(String[] args) {
        List<List<Integer>> arr2d = Arrays.asList(
            Arrays.asList(1, 1, 2, 5, 7, 6, 7, 7, 6, 3),
            Arrays.asList(8, 5, 4, 7, 5, 2, 6, 10, 1, 7),
            Arrays.asList(4, 3, 10, 4, 4, 4, 3, 1, 4, 3),
            Arrays.asList(1, 4, 1, 1, 8, 4, 9, 8, 5, 5),
            Arrays.asList(1, 1, 4, 4, 2, 10, 5, 6, 8, 1)
        );

        countfreq(arr2d);
    }
}

```

## Code (Python)

```python
def countfreq(arr2d):
    result = []
    for row in arr2d:
        freq = [0] * 10  # since student IDs are 1–10
        for val in row:
            if 1 <= val <= 10:
                freq[val - 1] += 1
        result.append(freq)
    print(result)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
