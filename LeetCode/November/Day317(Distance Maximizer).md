--- ❤️ ---

# 🚀 _Day 317. Distance Maximizer_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/distance-maximizer/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int id, x, y;
    string owner;

    long long maxDist = 0;

    while (cin >> id >> owner >> x >> y) {
        long long dist = abs(x - 20) + abs(y - 4);
        maxDist = max(maxDist, dist);
    }

    cout << maxDist;
    return 0;
}

```

## Code (Java)

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        long maxDist = 0;

        while (sc.hasNext()) {
            int id = sc.nextInt();
            String owner = sc.next();
            int x = sc.nextInt();
            int y = sc.nextInt();

            long dist = Math.abs(x - 20) + Math.abs(y - 4);
            maxDist = Math.max(maxDist, dist);
        }

        System.out.println(maxDist);
    }
}

```

## Code (Python)

```python
import sys

max_dist = 0

for line in sys.stdin:
    parts = line.strip().split()
    if len(parts) < 4:
        continue

    id = int(parts[0])
    owner = parts[1]
    x = int(parts[2])
    y = int(parts[3])

    dist = abs(x - 20) + abs(y - 4)
    max_dist = max(max_dist, dist)

print(max_dist)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
