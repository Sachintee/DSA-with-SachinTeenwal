--- ❤️ ---

# 🚀 _Day 177. Snake Ladder Problem!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/snake-ladder-problem/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <queue>
#include <unordered_map>
#include <unordered_set>

using namespace std;

class Solution {
public:
    int snakeLadder(vector<vector<int>>& A, vector<vector<int>>& B) {
        unordered_map<int, int> moves;
        for (const auto& ladder : A) {
            moves[ladder[0]] = ladder[1];
        }
        for (const auto& snake : B) {
            moves[snake[0]] = snake[1];
        }
        
        unordered_set<int> visited;
        queue<pair<int, int>> q; // {position, rolls}
        q.push({1, 0});
        visited.insert(1);
        
        while (!q.empty()) {
            auto current = q.front();
            q.pop();
            int pos = current.first;
            int rolls = current.second;
            
            if (pos == 100) {
                return rolls;
            }
            
            for (int i = 1; i <= 6; ++i) {
                int next_pos = pos + i;
                if (moves.find(next_pos) != moves.end()) {
                    next_pos = moves[next_pos];
                }
                if (next_pos <= 100 && visited.find(next_pos) == visited.end()) {
                    visited.insert(next_pos);
                    q.push({next_pos, rolls + 1});
                }
            }
        }
        return -1;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int snakeLadder(int[][] A, int[][] B) {
        Map<Integer, Integer> moves = new HashMap<>();
        for (int[] ladder : A) {
            moves.put(ladder[0], ladder[1]);
        }
        for (int[] snake : B) {
            moves.put(snake[0], snake[1]);
        }
        
        Set<Integer> visited = new HashSet<>();
        Queue<int[]> queue = new LinkedList<>(); // {position, rolls}
        queue.offer(new int[]{1, 0});
        visited.add(1);
        
        while (!queue.isEmpty()) {
            int[] current = queue.poll();
            int pos = current[0];
            int rolls = current[1];
            
            if (pos == 100) {
                return rolls;
            }
            
            for (int i = 1; i <= 6; ++i) {
                int nextPos = pos + i;
                if (moves.containsKey(nextPos)) {
                    nextPos = moves.get(nextPos);
                }
                if (nextPos <= 100 && !visited.contains(nextPos)) {
                    visited.add(nextPos);
                    queue.offer(new int[]{nextPos, rolls + 1});
                }
            }
        }
        return -1;
    }
}
```

## Code (Python)

```python
from collections import deque

class Solution:
    def snakeLadder(self, A, B):
        # Create a mapping for ladders and snakes
        moves = {}
        for start, end in A:
            moves[start] = end
        for start, end in B:
            moves[start] = end
        
        visited = set()
        queue = deque()
        queue.append((1, 0))  # (current_position, number_of_rolls)
        visited.add(1)
        
        while queue:
            pos, rolls = queue.popleft()
            if pos == 100:
                return rolls
            for i in range(1, 7):
                next_pos = pos + i
                if next_pos in moves:
                    next_pos = moves[next_pos]
                if next_pos <= 100 and next_pos not in visited:
                    visited.add(next_pos)
                    queue.append((next_pos, rolls + 1))
        return -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
