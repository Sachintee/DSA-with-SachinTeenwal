--- ❤️ ---

# 🚀 _Day 289. Sets in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/sets-in-c/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <set>
using namespace std;

int main() {
    // Declare a sorted set of integer type
    set<int> sortedSet;
    
    // Add all even numbers from 1 to 15
    for (int i = 1; i <= 15; i++) {
        if (i % 2 == 0) {
            sortedSet.insert(i);
        }
    }
    
    // Remove the largest element
    if (!sortedSet.empty()) {
        auto last = sortedSet.end();
        last--;
        sortedSet.erase(last);
    }
    
    // Remove the 2nd smallest element
    if (sortedSet.size() >= 2) {
        auto it = sortedSet.begin();
        it++; // Move to 2nd element
        sortedSet.erase(it);
    }
    
    // Insert first 5 odd numbers
    for (int i = 1; i <= 9; i += 2) {
        sortedSet.insert(i);
    }
    
    // Print the elements of the set separated by a space
    for (int num : sortedSet) {
        cout << num << " ";
    }
    cout << endl;
    
    // Print the size of the set
    cout << sortedSet.size() << endl;
    
    return 0;
}
```

## Code (Java)

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        // Declare a sorted set of integer type
        TreeSet<Integer> sortedSet = new TreeSet<>();
        
        // Add all even numbers from 1 to 15
        for (int i = 1; i <= 15; i++) {
            if (i % 2 == 0) {
                sortedSet.add(i);
            }
        }
        
        // Remove the largest element
        if (!sortedSet.isEmpty()) {
            sortedSet.remove(sortedSet.last());
        }
        
        // Remove the 2nd smallest element
        if (sortedSet.size() >= 2) {
            Iterator<Integer> it = sortedSet.iterator();
            it.next(); // Skip first element
            it.next(); // Now at 2nd element
            it.remove();
        }
        
        // Insert first 5 odd numbers
        for (int i = 1; i <= 9; i += 2) {
            sortedSet.add(i);
        }
        
        // Print the elements of the set separated by a space
        for (int num : sortedSet) {
            System.out.print(num + " ");
        }
        System.out.println();
        
        // Print the size of the set
        System.out.println(sortedSet.size());
    }
}
```

## Code (Python)

```python
def main():
    # Declare a sorted set of integer type
    sorted_set = set()
    
    # Add all even numbers from 1 to 15
    for i in range(1, 16):
        if i % 2 == 0:
            sorted_set.add(i)
    
    # Convert to sorted list for operations
    sorted_list = sorted(sorted_set)
    
    # Remove the largest element
    if sorted_list:
        sorted_list.pop()
    
    # Remove the 2nd smallest element
    if len(sorted_list) >= 2:
        sorted_list.pop(1)  # Remove element at index 1 (2nd smallest)
    
    # Insert first 5 odd numbers
    for i in range(1, 10, 2):
        sorted_list.append(i)
    
    # Convert back to set and then to sorted list for final output
    final_set = set(sorted_list)
    sorted_final = sorted(final_set)
    
    # Print the elements of the set separated by a space
    print(" ".join(map(str, sorted_final)))
    
    # Print the size of the set
    print(len(sorted_final))

if __name__ == "__main__":
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
