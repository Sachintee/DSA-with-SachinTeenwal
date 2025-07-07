--- ❤️ ---

# 🚀 _Day 188. List Comprehensions_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/list-comprehensions/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
#include <string>

int main() {
    std::vector<std::string> str_list = {"given", "intern", "InterviewBit", "network", "local", "multiple", "define", "nodes", "algorithm", "allows", "community", "phase", "single"};
    std::vector<std::string> my_list;

    for (const auto& s : str_list) {
        if (s.length() % 2 == 1) {
            my_list.push_back(s);
        }
    }

    std::cout << "[";
    for (size_t i = 0; i < my_list.size(); ++i) {
        std::cout << "\"" << my_list[i] << "\"";
        if (i != my_list.size() - 1) {
            std::cout << ", ";
        }
    }
    std::cout << "]" << std::endl;

    return 0;
}
```

## Code (Java)

```java
import java.util.ArrayList;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        List<String> strList = List.of("given", "intern", "InterviewBit", "network", "local", "multiple", "define", "nodes", "algorithm", "allows", "community", "phase", "single");
        List<String> myList = new ArrayList<>();

        for (String s : strList) {
            if (s.length() % 2 == 1) {
                myList.add(s);
            }
        }

        System.out.println(myList);
    }
}
```

## Code (Python)

```python
def main():
    str_list = ['given', 'intern', 'InterviewBit', 'network', 'local', 'multiple', 'define', 'nodes', 'algorithm', 'allows', 'community', 'phase', 'single']
    my_list = [s for s in str_list if len(s) % 2 == 1]
    
    print(my_list)
    return 0

if __name__ == '__main__':
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
