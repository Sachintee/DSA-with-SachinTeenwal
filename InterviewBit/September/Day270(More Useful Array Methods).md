--- ❤️ ---

# 🚀 _Day 270. More Useful Array Methods_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/more-useful-array-methods/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    int size_;
    cin >> size_;
    vector<int> array_(size_);
    
    for(int i = 0; i < size_; i++) {
        cin >> array_[i];
    }
    
    // Sort the array
    sort(array_.begin(), array_.end());
    
    // Print each element on a new line
    for(int i = 0; i < size_; i++) {
        cout << array_[i] << endl;
    }
    
    return 0;
}
```

## Code (Java)

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int size_ = scanner.nextInt();
        int[] array_ = new int[size_];
        
        for(int i = 0; i < size_; i++) {
            array_[i] = scanner.nextInt();
        }
        
        // Sort the array
        Arrays.sort(array_);
        
        // Print each element on a new line
        for(int i = 0; i < size_; i++) {
            System.out.println(array_[i]);
        }
    }
}
```

## Code (Python)

```python
# Read the size of the array
size_ = int(input().strip())
array_ = []

# Read array elements
for i in range(size_):
    x = int(input().strip())
    array_.append(x)

# Sort the array
array_.sort()

# Print each element on a new line
for num in array_:
    print(num)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
