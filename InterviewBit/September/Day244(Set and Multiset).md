--- ❤️ ---

# 🚀 _Day 244. Set and Multiset_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/set-and-multiset/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <set>
using namespace std;

int main() {
    int Q;
    cin >> Q;
    set<int> s;

    while (Q--) {
        int type, x;
        cin >> type >> x;

        if (type == 1) {
            // Insert x
            s.insert(x);
        }
        else if (type == 2) {
            // Erase x (only if present)
            s.erase(x);
        }
        else if (type == 3) {
            // Check if present
            if (s.find(x) != s.end())
                cout << "Yes" << endl;
            else
                cout << "No" << endl;
        }
    }

    // Print remaining elements if set not empty
    for (auto val : s) {
        cout << val << endl;
    }

    return 0;
}

```

## Code (Java)

```java
import java.util.*;
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int Q = sc.nextInt();
        TreeSet<Integer> set = new TreeSet<>();

        while (Q-- > 0) {
            int type = sc.nextInt();
            int x = sc.nextInt();

            if (type == 1) {
                set.add(x); // Insert
            } else if (type == 2) {
                set.remove(x); // Erase
            } else if (type == 3) {
                if (set.contains(x))
                    System.out.println("Yes");
                else
                    System.out.println("No");
            }
        }

        // Print remaining elements sorted
        for (int val : set) {
            System.out.println(val);
        }
    }
}

```

## Code (Python3)

```python
# Read number of queries
Q = int(input().strip())
s = set()

for _ in range(Q):
    query = list(map(int, input().split()))
    t, x = query[0], query[1]

    if t == 1:
        s.add(x)   # Insert
    elif t == 2:
        s.discard(x)  # Erase if exists
    elif t == 3:
        print("Yes" if x in s else "No")

# Print remaining elements sorted
for val in sorted(s):
    print(val)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
