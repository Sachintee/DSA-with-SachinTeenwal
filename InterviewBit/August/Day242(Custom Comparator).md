--- ❤️ ---

# 🚀 _Day 242. Custom Comparator_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/custom-comparator/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
using namespace std;

bool comp(pair<int, int> a, pair<int, int> b) {
    int sumA = a.first + a.second;
    int sumB = b.first + b.second;
    return sumA < sumB;
}

void sortArray(vector<pair<int, int>> &A){
    sort(A.begin(), A.end(), comp);
}
```

## Code (Java)

```java
import java.util.*;

public class Main {
    public static void sortArray(ArrayList<Pair<Integer, Integer>> A) {
        // Using custom comparator with lambda expression (Java 8+)
        Collections.sort(A, (a, b) -> (a.getKey() + a.getValue()) - (b.getKey() + b.getValue()));
        
        // Alternative using anonymous class (for older Java versions)
        /*
        Collections.sort(A, new Comparator<Pair<Integer, Integer>>() {
            @Override
            public int compare(Pair<Integer, Integer> a, Pair<Integer, Integer> b) {
                return (a.getKey() + a.getValue()) - (b.getKey() + b.getValue());
            }
        });
        */
    }
    
    // Helper Pair class (Java doesn't have built-in Pair like C++)
    static class Pair<K, V> {
        private K key;
        private V value;
        
        public Pair(K key, V value) {
            this.key = key;
            this.value = value;
        }
        
        public K getKey() { return key; }
        public V getValue() { return value; }
        
        @Override
        public String toString() {
            return "(" + key + ", " + value + ")";
        }
    }
    
    public static void main(String[] args) {
        ArrayList<Pair<Integer, Integer>> A = new ArrayList<>();
        A.add(new Pair<>(10, 5));
        A.add(new Pair<>(20, 25));
        A.add(new Pair<>(18, 18));
        A.add(new Pair<>(25, 4));
        
        sortArray(A);
        System.out.println(A);
        // Output: [(25, 4), (10, 5), (18, 18), (20, 25)]
    }
}
```

## Code (Python)

```python
def sort_array(A):
    # Using custom key function (more Pythonic way)
    A.sort(key=lambda x: x[0] + x[1])
    
    # Alternative using custom comparator (if needed for more complex logic)
    # import functools
    # def comp(a, b):
    #     return (a[0] + a[1]) - (b[0] + b[1])
    # A.sort(key=functools.cmp_to_key(comp))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
