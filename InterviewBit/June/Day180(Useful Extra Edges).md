--- ❤️ ---

# 🚀 _Day 180. Useful Extra Edges_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/useful-extra-edges/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <queue>
#include <climits>
#include <utility>

using namespace std;

class Solution {
public:
    int solve(int A, vector<vector<int>>& B, int C, int D, vector<vector<int>>& E) {
        // Build the graph
        vector<vector<pair<int, int>>> graph(A + 1);
        for (const auto& edge : B) {
            int u = edge[0];
            int v = edge[1];
            int w = edge[2];
            graph[u].emplace_back(v, w);
            graph[v].emplace_back(u, w);
        }
        
        auto dijkstra = [&](int start) {
            vector<int> dist(A + 1, INT_MAX);
            dist[start] = 0;
            priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
            pq.emplace(0, start);
            
            while (!pq.empty()) {
                int current_dist = pq.top().first;
                int u = pq.top().second;
                pq.pop();
                
                if (current_dist > dist[u]) {
                    continue;
                }
                
                for (const auto& neighbor : graph[u]) {
                    int v = neighbor.first;
                    int w = neighbor.second;
                    if (dist[v] > current_dist + w) {
                        dist[v] = current_dist + w;
                        pq.emplace(dist[v], v);
                    }
                }
            }
            return dist;
        };
        
        vector<int> dist_C = dijkstra(C);
        vector<int> dist_D = dijkstra(D);
        
        if (dist_C[D] == INT_MAX) {
            return -1;
        }
        
        int min_dist = dist_C[D];
        
        for (const auto& edge : E) {
            int u = edge[0];
            int v = edge[1];
            int w = edge[2];
            
            if (dist_C[u] != INT_MAX && dist_D[v] != INT_MAX) {
                min_dist = min(min_dist, dist_C[u] + w + dist_D[v]);
            }
            if (dist_C[v] != INT_MAX && dist_D[u] != INT_MAX) {
                min_dist = min(min_dist, dist_C[v] + w + dist_D[u]);
            }
        }
        
        return min_dist != INT_MAX ? min_dist : -1;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(int A, int[][] B, int C, int D, int[][] E) {
        // Build the graph
        List<List<int[]>> graph = new ArrayList<>();
        for (int i = 0; i <= A; i++) {
            graph.add(new ArrayList<>());
        }
        for (int[] edge : B) {
            int u = edge[0];
            int v = edge[1];
            int w = edge[2];
            graph.get(u).add(new int[]{v, w});
            graph.get(v).add(new int[]{u, w});
        }
        
        int[] dijkstra(int start) {
            int[] dist = new int[A + 1];
            Arrays.fill(dist, Integer.MAX_VALUE);
            dist[start] = 0;
            PriorityQueue<int[]> pq = new PriorityQueue<>(Comparator.comparingInt(a -> a[1]));
            pq.add(new int[]{start, 0});
            
            while (!pq.isEmpty()) {
                int[] current = pq.poll();
                int u = current[0];
                int currentDist = current[1];
                
                if (currentDist > dist[u]) {
                    continue;
                }
                
                for (int[] neighbor : graph.get(u)) {
                    int v = neighbor[0];
                    int w = neighbor[1];
                    if (dist[v] > currentDist + w) {
                        dist[v] = currentDist + w;
                        pq.add(new int[]{v, dist[v]});
                    }
                }
            }
            return dist;
        }
        
        int[] distC = dijkstra(C);
        int[] distD = dijkstra(D);
        
        if (distC[D] == Integer.MAX_VALUE) {
            return -1;
        }
        
        int minDist = distC[D];
        
        for (int[] edge : E) {
            int u = edge[0];
            int v = edge[1];
            int w = edge[2];
            
            if (distC[u] != Integer.MAX_VALUE && distD[v] != Integer.MAX_VALUE) {
                minDist = Math.min(minDist, distC[u] + w + distD[v]);
            }
            if (distC[v] != Integer.MAX_VALUE && distD[u] != Integer.MAX_VALUE) {
                minDist = Math.min(minDist, distC[v] + w + distD[u]);
            }
        }
        
        return minDist != Integer.MAX_VALUE ? minDist : -1;
    }
}
```

## Code (Python)

```python
import heapq

class Solution:
    def solve(self, A, B, C, D, E):
        # Build the graph
        graph = [[] for _ in range(A + 1)]
        for u, v, w in B:
            graph[u].append((v, w))
            graph[v].append((u, w))
        
        def dijkstra(start):
            dist = [float('inf')] * (A + 1)
            dist[start] = 0
            heap = [(0, start)]
            visited = set()
            
            while heap:
                current_dist, u = heapq.heappop(heap)
                if u in visited:
                    continue
                visited.add(u)
                for v, w in graph[u]:
                    if dist[v] > current_dist + w:
                        dist[v] = current_dist + w
                        heapq.heappush(heap, (dist[v], v))
            return dist
        
        dist_C = dijkstra(C)
        dist_D = dijkstra(D)
        
        if dist_C[D] == float('inf'):
            return -1
        
        min_dist = dist_C[D]
        
        for u, v, w in E:
            if dist_C[u] != float('inf') and dist_D[v] != float('inf'):
                min_dist = min(min_dist, dist_C[u] + w + dist_D[v])
            if dist_C[v] != float('inf') and dist_D[u] != float('inf'):
                min_dist = min(min_dist, dist_C[v] + w + dist_D[u])
        
        return min_dist if min_dist != float('inf') else -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
