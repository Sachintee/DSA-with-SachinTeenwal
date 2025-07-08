--- ❤️ ---

# 🚀 _Day 189. Numpy Arrays_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/numpy-arrays/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> arr = {1, 3, 2, 2, 5, 3, 8, 2};
    std::vector<int> indices;

    for (int i = 0; i < arr.size(); ++i) {
        if (arr[i] == 2) {
            indices.push_back(i);
        }
    }

    std::cout << "Indices of 2: ";
    for (int idx : indices) {
        std::cout << idx << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

## Code (Java)

```java
import java.util.ArrayList;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        int[] arr = {1, 3, 2, 2, 5, 3, 8, 2};
        List<Integer> indices = new ArrayList<>();

        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == 2) {
                indices.add(i);
            }
        }

        System.out.print("Indices of 2: ");
        for (int idx : indices) {
            System.out.print(idx + " ");
        }
        System.out.println();
    }
}
```

## Code (Python)

```python
import numpy as np

def main():
    arr = [1, 3, 2, 2, 5, 3, 8, 2]
    
    # Convert the above array into ndarray
    arr = np.array(arr)
    
    print(type(arr))
    
    # Use where to find all the indexes of 2
    x = np.where(arr == 2)
    
    print(x)
    return 0

if __name__ == '__main__':
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
