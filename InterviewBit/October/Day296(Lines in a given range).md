--- ❤️ ---

# 🚀 _Day 296. Lines in a given range_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/lines-in-a-given-range/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <fstream>
#include <string>
#include <vector>
using namespace std;

int main() {
    ifstream file("input");
    if (!file.is_open()) return 0;

    vector<string> lines;
    string line;

    while (getline(file, line)) {
        lines.push_back(line);
    }
    file.close();

    if (lines.empty()) return 0;

    int l, r;
    {
        string firstLine = lines[0];
        sscanf(firstLine.c_str(), "%d %d", &l, &r);
    }

    int n = lines.size();
    for (int i = l; i <= r && i <= n; i++) {
        cout << lines[i - 1] << endl; // 1-based indexing
    }

    return 0;
}

```

## Code (Java)

```java
import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        BufferedReader br = new BufferedReader(new FileReader("input"));
        List<String> lines = new ArrayList<>();
        String line;

        while ((line = br.readLine()) != null) {
            lines.add(line);
        }
        br.close();

        if (lines.size() == 0) return;

        String[] range = lines.get(0).split(" ");
        int l = Integer.parseInt(range[0]);
        int r = Integer.parseInt(range[1]);

        for (int i = l; i <= r && i <= lines.size(); i++) {
            System.out.println(lines.get(i - 1)); // 1-based line indexing
        }
    }
}

```

## Code (Python)

```python
def main():
    # Read all lines from 'input' file (preserve order)
    with open("input", "r") as f:
        lines = [line.rstrip("\n") for line in f.readlines()]

    if not lines:
        return

    # First line contains l and r
    parts = lines[0].strip().split()
    if len(parts) < 2:
        return

    l, r = map(int, parts)

    # Print file lines l..r inclusive (1-based). lines[0] is the header.
    # So lines[l-1] .. lines[r-1]
    n = len(lines)
    start = max(1, l)    # ensure at least 1
    end = min(r, n)      # don't go past file end

    for idx in range(start, end + 1):
        # idx is 1-based line number in the file
        print(lines[idx - 1])

if __name__ == '__main__':
    main()

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
