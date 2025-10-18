--- ❤️ ---

# 🚀 _Day 291. Generics in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/generics-in-c/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

template <typename T>
class Printer {
public:
    void printArray(T arr[], int n) {
        for (int i = 0; i < n; i++) {
            cout << arr[i] << endl;
        }
    }
};

int main() {
    // Example usage (judge may handle input itself)
    Printer<int> intPrinter;
    int intArr[] = {1, 2, 3};
    intPrinter.printArray(intArr, 3);

    Printer<string> stringPrinter;
    string strArr[] = {"Hello", "World"};
    stringPrinter.printArray(strArr, 2);
    return 0;
}

```

## Code (Java)

```java
class Printer<T> {
    void printArray(T[] arr) {
        for (T item : arr) {
            System.out.println(item);
        }
    }

    public static void main(String[] args) {
        // Example usage (judge may handle input itself)
        Printer<Integer> intPrinter = new Printer<>();
        Integer[] intArr = {1, 2, 3};
        intPrinter.printArray(intArr);

        Printer<String> stringPrinter = new Printer<>();
        String[] strArr = {"Hello", "World"};
        stringPrinter.printArray(strArr);
    }
}

```

## Code (Python)

```python
class Printer:
    def printArray(self, arr):
        for item in arr:
            print(item)

# Example usage (judge may handle input itself)
if __name__ == "__main__":
    p = Printer()
    p.printArray([1, 2, 3])
    p.printArray(["Hello", "World"])

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
