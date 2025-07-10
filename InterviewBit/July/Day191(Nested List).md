--- ❤️ ---

# 🚀 _Day 191. Nested List_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/nested-list/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>

int main() {
    std::vector<std::vector<std::vector<std::string>>> my_list = {
        {{"a"}, {"b"}},
        {{"cc"}, {"dd"}, {"eee", "fff"}},
        {{"g"}, {"h"}}
    };

    // Insert a new list [1, 2, 3] at the end of my_list
    my_list.push_back({{"1"}, {"2"}, {"3"}});

    // Print the list after insertion
    std::cout << "After insertion:" << std::endl;
    for (const auto& sublist : my_list) {
        std::cout << "[";
        for (const auto& item : sublist) {
            std::cout << "[";
            for (const auto& elem : item) {
                std::cout << elem << " ";
            }
            std::cout << "]";
        }
        std::cout << "]" << std::endl;
    }

    // Delete 'eee' from the list
    auto& nested_list = my_list[1][2];
    auto it = std::find(nested_list.begin(), nested_list.end(), "eee");
    if (it != nested_list.end()) {
        nested_list.erase(it);
    }

    // Print the list after deletion
    std::cout << "After deletion:" << std::endl;
    for (const auto& sublist : my_list) {
        std::cout << "[";
        for (const auto& item : sublist) {
            std::cout << "[";
            for (const auto& elem : item) {
                std::cout << elem << " ";
            }
            std::cout << "]";
        }
        std::cout << "]" << std::endl;
    }

    return 0;
}
```

## Code (Java)

```java
import java.util.ArrayList;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        List<List<List<String>>> myList = new ArrayList<>();
        myList.add(new ArrayList<>() {{
            add(new ArrayList<>(List.of("a")));
            add(new ArrayList<>(List.of("b")));
        }});
        myList.add(new ArrayList<>() {{
            add(new ArrayList<>(List.of("cc")));
            add(new ArrayList<>(List.of("dd")));
            add(new ArrayList<>(List.of("eee", "fff")));
        }});
        myList.add(new ArrayList<>() {{
            add(new ArrayList<>(List.of("g")));
            add(new ArrayList<>(List.of("h")));
        }});

        // Insert a new list [1, 2, 3] at the end of myList
        myList.add(new ArrayList<>() {{
            add(new ArrayList<>(List.of("1")));
            add(new ArrayList<>(List.of("2")));
            add(new ArrayList<>(List.of("3")));
        }});

        // Print the list after insertion
        System.out.println("After insertion:");
        System.out.println(myList);

        // Delete 'eee' from the list
        myList.get(1).get(2).remove("eee");

        // Print the list after deletion
        System.out.println("After deletion:");
        System.out.println(myList);
    }
}
```

## Code (Python)

```python
def main():
    my_list = [['a', 'b'], ['cc', 'dd', ['eee', 'fff']], ['g', 'h']]
    
    # insert a new list [1, 2, 3] at the end of my_list
    my_list.append([1, 2, 3])
    
    print(my_list)
    
    # Delete 'eee' from the list
    my_list[1][2].remove('eee')
    
    print(my_list)
    return 0
    
if __name__ == '__main__':
    main()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
