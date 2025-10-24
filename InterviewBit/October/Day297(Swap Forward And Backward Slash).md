--- ❤️ ---

# 🚀 _Day 297. Swap Forward And Backward Slash_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/swap-forward-and-backward-slash/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ifstream file("input");
    char ch;
    while (file.get(ch)) {
        if (ch == '/')
            cout << '\\';
        else if (ch == '\\')
            cout << '/';
        else
            cout << ch;
    }
    return 0;
}

```

## Code (Java)

```java
import java.io.*;

public class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new FileReader("input"));
        int c;
        while ((c = br.read()) != -1) {
            char ch = (char) c;
            if (ch == '/')
                System.out.print('\\');
            else if (ch == '\\')
                System.out.print('/');
            else
                System.out.print(ch);
        }
    }
}

```

## Code (Python)

```python
import os

def main():
    # Replace all '\' with '/' and all '/' with '\'
    os.system("cat input | tr '/\\\\' '\\\\/'")

if __name__ == '__main__':
    main()

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
