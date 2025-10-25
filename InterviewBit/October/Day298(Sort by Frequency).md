--- ❤️ ---

# 🚀 _Day 298. Sort by Frequency_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/sort-by-frequency/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <fstream>
#include <sstream>
#include <map>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    ifstream file("input");
    string word, line;
    map<string, int> freq;

    while (file >> word) freq[word]++;

    map<int, vector<string>> grouped;
    for (auto &p : freq) grouped[p.second].push_back(p.first);

    for (auto &g : grouped) {
        sort(g.second.begin(), g.second.end());
        cout << g.first;
        for (auto &w : g.second) cout << " " << w;
        cout << endl;
    }
    return 0;
}

```

## Code (Java)

```java
import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new FileReader("input"));
        String line;
        Map<String, Integer> freq = new HashMap<>();

        while ((line = br.readLine()) != null) {
            for (String w : line.split("\\s+")) {
                if (!w.isEmpty())
                    freq.put(w, freq.getOrDefault(w, 0) + 1);
            }
        }

        Map<Integer, List<String>> grouped = new TreeMap<>();
        for (Map.Entry<String, Integer> e : freq.entrySet()) {
            grouped.computeIfAbsent(e.getValue(), k -> new ArrayList<>()).add(e.getKey());
        }

        for (Map.Entry<Integer, List<String>> e : grouped.entrySet()) {
            Collections.sort(e.getValue());
            System.out.print(e.getKey());
            for (String w : e.getValue())
                System.out.print(" " + w);
            System.out.println();
        }
    }
}

```

## Code (Python)

```python
def main():
    with open("input", "r") as f:
        words = f.read().split()

    freq = {}
    for w in words:
        freq[w] = freq.get(w, 0) + 1

    # Group words by frequency
    grouped = {}
    for word, count in freq.items():
        grouped.setdefault(count, []).append(word)

    # Sort frequencies and words
    for count in sorted(grouped.keys()):
        print(count, *sorted(grouped[count]))

if __name__ == '__main__':
    main()

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
