--- ❤️ ---

# 🚀 _Day 300. Transform CSV_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/transform-csv/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <fstream>
#include <sstream>
#include <vector>
using namespace std;

int main() {
    ifstream fin("input");
    string line;

    while (getline(fin, line)) {
        stringstream ss(line);
        string first, last, address, city, code, email, phone;
        getline(ss, first, ',');
        getline(ss, last, ',');
        getline(ss, address, ',');
        getline(ss, city, ',');
        getline(ss, code, ',');
        getline(ss, email, ',');
        getline(ss, phone, ',');

        cout << first << "," << last << "," << address << "," << city << ","
             << email << ",+" << code << "-" << phone << endl;
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
        String line;

        while ((line = br.readLine()) != null) {
            String[] parts = line.split(",", 7); // Split into 7 parts
            String first = parts[0];
            String last = parts[1];
            String address = parts[2];
            String city = parts[3];
            String code = parts[4];
            String email = parts[5];
            String phone = parts[6];

            System.out.println(first + "," + last + "," + address + "," + city + "," +
                               email + ",+" + code + "-" + phone);
        }
        br.close();
    }
}

```

## Code (Python)

```python
def main():
    with open("input", "r") as f:
        for line in f:
            parts = line.strip().split(",")
            if len(parts) == 7:
                first, last, address, city, code, email, phone = parts
                print(f"{first},{last},{address},{city},{email},+{code}-{phone}")

if __name__ == "__main__":
    main()

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
