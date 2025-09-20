--- ❤️ ---

# 🚀 _Day 263. HashSets_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/hashsets/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <unordered_set>
using namespace std;

int main() {
    int n;
    cin >> n;
    
    unordered_set<int> uniqueSet;
    
    for (int i = 0; i < n; i++) {
        int num;
        cin >> num;
        uniqueSet.insert(num);
    }
    
    cout << uniqueSet.size() << endl;
    
    return 0;
}
```

## Code (Java)

```java
import java.lang.*;
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        
        // Use HashSet to store unique elements
        Set<Integer> uniqueSet = new HashSet<>();
        
        for (int i = 0; i < n; i++) {
            int num = scanner.nextInt();
            uniqueSet.add(num);
        }
        
        // The size of the set gives the number of unique elements
        System.out.println(uniqueSet.size());
        
        scanner.close();
    }
}
```

## Code (Python)

```python
def main():
    n = int(input())
    unique_set = set()
    
    for _ in range(n):
        num = int(input())
        unique_set.add(num)
    
    print(len(unique_set))

if __name__ == "__main__":
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
