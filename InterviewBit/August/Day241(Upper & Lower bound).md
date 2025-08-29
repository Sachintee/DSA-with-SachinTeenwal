--- ❤️ ---

# 🚀 _Day 241. Upper & Lower bound_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/upper-lower-bound/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;

int main() {
    int N;
    cin >> N;
    vector<int> v(N);
    for (int i = 0; i < N; i++) {
        cin >> v[i];
    }
    
    int Q;
    cin >> Q;
    while (Q--) {
        int X;
        cin >> X;
        // find lower bound index
        int idx = lower_bound(v.begin(), v.end(), X) - v.begin();
        
        if (idx < N && v[idx] == X) {
            cout << idx << endl;   // element found
        } else {
            cout << idx << endl;   // insertion point
        }
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
        
        int N = sc.nextInt();
        int[] arr = new int[N];
        for (int i = 0; i < N; i++) {
            arr[i] = sc.nextInt();
        }
        
        int Q = sc.nextInt();
        while (Q-- > 0) {
            int X = sc.nextInt();
            int idx = Arrays.binarySearch(arr, X);
            
            if (idx >= 0) {
                // found exact match
                // move left to find first occurrence
                while (idx > 0 && arr[idx - 1] == X) {
                    idx--;
                }
                System.out.println(idx);
            } else {
                // not found → insertion point
                int insertionPoint = -(idx + 1);
                System.out.println(insertionPoint);
            }
        }
        sc.close();
    }
}
```

## Code (Python)

```python
import bisect

def main():
    N = int(input().strip())
    arr = list(map(int, input().split()))
    Q = int(input().strip())
    
    for _ in range(Q):
        X = int(input().strip())
        idx = bisect.bisect_left(arr, X)  # same as lower_bound
        
        if idx < N and arr[idx] == X:
            print(idx)   # element found
        else:
            print(idx)   # insertion index

if __name__ == "__main__":
    main()

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
