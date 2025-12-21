--- ❤️ ---

# 🚀 _Day 355. Famous Books_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/famous-books/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> boughtBooks = {50, 50, 50, 52, 52, 52, 52};

    unordered_map<int, int> freq;
    for (int id : boughtBooks) {
        freq[id]++;
    }

    for (auto &p : freq) {
        if (p.second >= 3) {
            cout << p.first << endl;
        }
    }
}

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
