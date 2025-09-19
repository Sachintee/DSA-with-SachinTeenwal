--- ❤️ ---

# 🚀 _Day 262. Generics_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/generics/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
#include <string>
using namespace std;

class Printer {
public:
    template <typename T>
    void printArray(vector<T> arr) {
        for (const auto& element : arr) {
            cout << element << endl;
        }
    }
};

int main() {
    Printer myPrinter;
    vector<int> intArray = {1, 2, 3};
    vector<string> stringArray = {"Hello", "World"};
    
    myPrinter.printArray(intArray);
    myPrinter.printArray(stringArray);
    
    return 0;
}
```

## Code (Java)

```java
import java.lang.*;
import java.util.*;
import java.io.IOException;
import java.lang.reflect.Method;

class Printer {
    // Generic method to print arrays of any type
    public <T> void printArray(T[] array) {
        for (T element : array) {
            System.out.println(element);
        }
    }
}

/*****Don't change anything in the code below*****/
public class Main {
    public static void main(String[] args) {
        Printer myPrinter = new Printer();
        Integer[] intArray = { 1, 2, 3 };
        String[] stringArray = {"Hello", "World"};
        myPrinter.printArray(intArray);
        myPrinter.printArray(stringArray);
        int count = 0;

        for (Method method : Printer.class.getDeclaredMethods()) {
            String name = method.getName();

            if(name.equals("printArray"))
                count++;
        }

        if(count > 1)System.out.println("Method overloading is not allowed!");
        
    }
}
```

## Code (Python)

```python
from typing import List, TypeVar

T = TypeVar('T')

class Printer:
    def printArray(self, arr: List[T]) -> None:
        for element in arr:
            print(element)

if __name__ == "__main__":
    my_printer = Printer()
    int_array = [1, 2, 3]
    string_array = ["Hello", "World"]
    
    my_printer.printArray(int_array)
    my_printer.printArray(string_array)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
