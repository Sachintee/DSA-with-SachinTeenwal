--- ❤️ ---

# 🚀 _Day 252. Deque_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/deque/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <deque>
using namespace std;

int main() {
    int Q;
    cin >> Q;
    deque<int> dq;
    
    for (int i = 0; i < Q; i++) {
        int x, y;
        cin >> x >> y;
        
        if (x == 1) {
            dq.push_back(y);  // Push y to the back
        } else if (x == 2) {
            dq.push_front(y); // Push y to the front
        } else if (x == 3) {
            if (dq.empty()) {
                cout << -1 << endl;
            } else {
                cout << dq.front() << endl;
            }
        } else if (x == 4) {
            if (dq.empty()) {
                cout << -1 << endl;
            } else {
                cout << dq.back() << endl;
            }
        } else if (x == 5) {
            if (!dq.empty()) {
                dq.pop_front();
            }
        } else if (x == 6) {
            if (!dq.empty()) {
                dq.pop_back();
            }
        }
    }
    
    return 0;
}

```

## Code (Java)

```java
import java.lang.*;
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner inp = new Scanner(System.in);
        int Q = inp.nextInt();
        
        Deque<Integer> deque = new ArrayDeque<>();
        
        for (int i = 0; i < Q; i++) {
            int x = inp.nextInt();
            int y = inp.nextInt();
            
            if (x == 1) {
                deque.addLast(y);  // Push y to the back
            } else if (x == 2) {
                deque.addFirst(y); // Push y to the front
            } else if (x == 3) {
                if (deque.isEmpty()) {
                    System.out.println("-1");
                } else {
                    System.out.println(deque.peekFirst());
                }
            } else if (x == 4) {
                if (deque.isEmpty()) {
                    System.out.println("-1");
                } else {
                    System.out.println(deque.peekLast());
                }
            } else if (x == 5) {
                if (!deque.isEmpty()) {
                    deque.removeFirst();
                }
            } else if (x == 6) {
                if (!deque.isEmpty()) {
                    deque.removeLast();
                }
            }
        }
        
        inp.close();
    }
}

```

## Code (Python)

```python
from collections import deque

Q = int(input())
dq = deque()

for _ in range(Q):
    x, y = map(int, input().split())
    
    if x == 1:
        dq.append(y)         # Push y to the back
    elif x == 2:

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
