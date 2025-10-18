--- ❤️ ---

# 🚀 _Day 290. Stack in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/stack-in-c/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <stack>
using namespace std;

int main() {
    // Declare a stack of integer type
    stack<int> st;
    
    // Push the first 5 even numbers in the stack
    for (int i = 2; i <= 10; i += 2) {
        st.push(i);
    }
    
    // Push the first 5 odd numbers in the stack
    for (int i = 1; i <= 9; i += 2) {
        st.push(i);
    }
    
    // Print the size of the stack
    cout << st.size() << endl;
    
    // Remove the top most element of the stack
    st.pop();
    
    // Print the elements of the stack from top to bottom
    // separated by space
    // Note: C++ stack doesn't support direct iteration, so we need to pop elements
    stack<int> temp = st;
    while (!temp.empty()) {
        cout << temp.top() << " ";
        temp.pop();
    }
    cout << endl;
    
    return 0;
}
```

## Code (Java)

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        // Declare a stack of integer type
        Stack<Integer> stack = new Stack<>();
        
        // Push the first 5 even numbers in the stack
        for (int i = 2; i <= 10; i += 2) {
            stack.push(i);
        }
        
        // Push the first 5 odd numbers in the stack
        for (int i = 1; i <= 9; i += 2) {
            stack.push(i);
        }
        
        // Print the size of the stack
        System.out.println(stack.size());
        
        // Remove the top most element of the stack
        stack.pop();
        
        // Print the elements of the stack from top to bottom
        // separated by space
        // Java Stack extends Vector, so we can iterate directly
        for (int i = stack.size() - 1; i >= 0; i--) {
            System.out.print(stack.get(i) + " ");
        }
        System.out.println();
    }
}
```

## Code (Python)

```python
def main():
    # Declare a stack of integer type
    stack = []
    
    # Push the first 5 even numbers in the stack
    for i in range(2, 11, 2):
        stack.append(i)
    
    # Push the first 5 odd numbers in the stack
    for i in range(1, 10, 2):
        stack.append(i)
    
    # Print the size of the stack
    print(len(stack))
    
    # Remove the top most element of the stack
    stack.pop()
    
    # Print the elements of the stack from top to bottom
    # separated by space
    # Reverse to print from top to bottom
    print(' '.join(map(str, reversed(stack))))

if __name__ == "__main__":
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

