--- ❤️ ---

# 🚀 _Day 268. Basic Array Methods_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/basic-array-methods/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    int size1, size2;
    
    // Read array A
    cin >> size1;
    vector<int> A(size1);
    for(int i = 0; i < size1; i++) {
        cin >> A[i];
    }
    
    // Read array B
    cin >> size2;
    vector<int> B(size2);
    for(int i = 0; i < size2; i++) {
        cin >> B[i];
    }
    
    // Remove first element from A and add to B
    if(!A.empty()) {
        int firstElement = A[0];
        // Remove first element by creating new vector without first element
        vector<int> newA(A.begin() + 1, A.end());
        
        // Add first element to B
        B.push_back(firstElement);
        
        // Merge arrays
        vector<int> ans;
        ans.insert(ans.end(), newA.begin(), newA.end());
        ans.insert(ans.end(), B.begin(), B.end());
        
        // Print result
        for(int num : ans) {
            cout << num << endl;
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
        
        // Read array A
        int size1 = sc.nextInt();
        ArrayList<Integer> A = new ArrayList<>();
        for(int i = 0; i < size1; i++) {
            A.add(sc.nextInt());
        }
        
        // Read array B
        int size2 = sc.nextInt();
        ArrayList<Integer> B = new ArrayList<>();
        for(int i = 0; i < size2; i++) {
            B.add(sc.nextInt());
        }
        
        // Remove first element from A and add to B
        if(!A.isEmpty()) {
            int firstElement = A.remove(0);
            B.add(firstElement);
            
            // Merge arrays
            ArrayList<Integer> ans = new ArrayList<>();
            ans.addAll(A);
            ans.addAll(B);
            
            // Print result
            for(int num : ans) {
                System.out.println(num);
            }
        }
        
        sc.close();
    }
}
```

## Code (Python)

```python
# Read array A
size1 = int(input().strip())
A = []
for i in range(size1):
    A.append(int(input().strip()))

# Read array B
size2 = int(input().strip())
B = []
for i in range(size2):
    B.append(int(input().strip()))

# Remove first element from A and add to B
if A:
    first_element = A.pop(0)
    B.append(first_element)
    
    # Merge arrays
    ans = A + B
    
    # Print result
    for num in ans:
        print(num)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
