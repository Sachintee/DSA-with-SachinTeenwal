--- ❤️ ---

# 🚀 _Day 186. String Operations_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/string-operations/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string S;
    getline(cin, S);
    
    // Print length of the string S
    cout << S.length() << endl;
    
    // Print the first occurrence of the letter 'a' in S
    cout << S.find('a') << endl;
    
    // Print all the characters with even index in S
    for (int i = 0; i < S.length(); i += 2) {
        cout << S[i];
    }
    cout << endl;
    
    return 0;
}
```

## Code (Java)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String S = scanner.nextLine();
        
        // Print length of the string S
        System.out.println(S.length());
        
        // Print the first occurrence of the letter 'a' in S
        System.out.println(S.indexOf('a'));
        
        // Print all the characters with even index in S
        for (int i = 0; i < S.length(); i += 2) {
            System.out.print(S.charAt(i));
        }
        System.out.println();
        
        scanner.close();
    }
}
```

## Code (Python)

```python
def main():
    S = input()
    
    # Print length of the string S
    print(len(S))
    
    # Print the first occurrence of the letter 'a' in S
    print(S.index('a'))
    
    # Print all the characters with even index in S
    print(S[::2])

if __name__ == '__main__':
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
