--- ❤️ ---

# 🚀 _Day 193. Collections Module I_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/collections-module-i/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <unordered_map>
#include <vector>

using namespace std;

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(nullptr);
    
    int N;
    cin >> N;
    
    vector<int> chocolate_types(N);
    for (int i = 0; i < N; ++i) {
        cin >> chocolate_types[i];
    }
    
    unordered_map<int, int> freq;
    for (int typ : chocolate_types) {
        freq[typ]++;
    }
    
    int M;
    cin >> M;
    
    long long total = 0;
    
    for (int i = 0; i < M; ++i) {
        int X, desired_type;
        cin >> X >> desired_type;
        
        if (freq[desired_type] > 0) {
            total += X;
            freq[desired_type]--;
        }
    }
    
    cout << total << endl;
    
    return 0;
}
```

## Code (Java)

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        int N = scanner.nextInt();
        
        int[] chocolateTypes = new int[N];
        for (int i = 0; i < N; i++) {
            chocolateTypes[i] = scanner.nextInt();
        }
        
        Map<Integer, Integer> freq = new HashMap<>();
        for (int typ : chocolateTypes) {
            freq.put(typ, freq.getOrDefault(typ, 0) + 1);
        }
        
        int M = scanner.nextInt();
        
        long total = 0;
        
        for (int i = 0; i < M; i++) {
            int X = scanner.nextInt();
            int desiredType = scanner.nextInt();
            
            if (freq.getOrDefault(desiredType, 0) > 0) {
                total += X;
                freq.put(desiredType, freq.get(desiredType) - 1);
            }
        }
        
        System.out.println(total);
        
        scanner.close();
    }
}
```

## Code (Python)

```python
from collections import defaultdict

def main():
    import sys
    input = sys.stdin.read
    data = input().split()
    
    idx = 0
    N = int(data[idx])
    idx += 1
    
    chocolate_types = list(map(int, data[idx:idx+N]))
    idx += N
    
    M = int(data[idx])
    idx += 1
    
    # Create a frequency dictionary for chocolate types
    freq = defaultdict(int)
    for typ in chocolate_types:
        freq[typ] += 1
    
    total = 0
    
    for _ in range(M):
        X = int(data[idx])
        desired_type = int(data[idx+1])
        idx += 2
        
        if freq.get(desired_type, 0) > 0:
            total += X
            freq[desired_type] -= 1
    
    print(total)

if __name__ == '__main__':
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
