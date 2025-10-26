--- ❤️ ---

# 🚀 _Day 299. Remove Punctuations_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/remove-punctuations/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <fstream>
#include <cctype>
using namespace std;

int main() {
    ifstream file("input");
    if (!file) return 0;

    string line;
    while (getline(file, line)) {
        for (char c : line) {
            if (!ispunct(c)) cout << c;
        }
        cout << endl;
    }

    return 0;
}

```

## Code (Java)

```java
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception {
        BufferedReader br = new BufferedReader(new FileReader("input"));
        String line;
        while ((line = br.readLine()) != null) {
            // Remove all punctuation using regex
            line = line.replaceAll("\\p{Punct}", "");
            System.out.println(line);
        }
        br.close();
    }
}

```

## Code (Python)

```python
import os

def main():
    # Remove punctuation marks and print cleaned content
    os.system("cat input | tr -d '[:punct:]'")

if __name__ == '__main__':
    main()

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
