--- ❤️ ---

# 🚀 _Day 253. PriorityQueue Comparator_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/priorityqueue-comparator/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <queue>

using namespace std;

int main() {
    int Q;
    cin >> Q;

    priority_queue<int> maxHeap;

    for (int i = 0; i < Q; i++) {
        int x, y;
        cin >> x >> y;

        if (x == 1) {
            // Insert y into maxHeap
            maxHeap.push(y);
        } else if (x == 2) {
            // Print max element or -1 if empty
            if (maxHeap.empty()) {
                cout << -1 << endl;
            } else {
                cout << maxHeap.top() << endl;
            }
        } else if (x == 3) {
            // Remove max element if present
            if (!maxHeap.empty()) {
                maxHeap.pop();
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
        
        // Correct way to define max heap
        PriorityQueue<Integer> maxHeap = new PriorityQueue<Integer>(100000, Collections.reverseOrder());

        for (int i = 0; i < Q; i++) {
            int x = inp.nextInt();
            int y = inp.nextInt();
            
            if (x == 1) {
                // Insert y into the max heap
                maxHeap.add(y);
            } else if (x == 2) {
                // Print max element or -1 if empty
                if (maxHeap.isEmpty()) {
                    System.out.println("-1");
                } else {
                    System.out.println(maxHeap.peek());
                }
            } else if (x == 3) {
                // Remove max element if present
                if (!maxHeap.isEmpty()) {
                    maxHeap.poll();
                }
            }
        }
        
        inp.close();
    }
}

```

## Code (Python3)

```python
import heapq
import sys

input = sys.stdin.read
data = input().split()

Q = int(data[0])
queries = data[1:]

max_heap = []

index = 0
for _ in range(Q):
    x = int(queries[index])
    y = int(queries[index + 1])
    index += 2

    if x == 1:
        # Insert y into max heap (store as negative for max-heap behavior)
        heapq.heappush(max_heap, -y)
    elif x == 2:
        # Print max element or -1 if empty
        if max_heap:
            print(-max_heap[0])
        else:
            print(-1)
    elif x == 3:
        # Remove max element if present
        if max_heap:
            heapq.heappop(max_heap)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
