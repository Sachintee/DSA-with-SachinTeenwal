--- ❤️ ---

# 🚀 _Day 132. Shortest Unique Prefix_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/shortest-unique-prefix/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>
#include <unordered_map>

using namespace std;

class TrieNode {
public:
    unordered_map<char, TrieNode*> children;
    int count;
    TrieNode() : count(0) {}
};

class Solution {
public:
    vector<string> prefix(vector<string> &A) {
        TrieNode* root = new TrieNode();
        // Insert all words into the trie
        for (const string &word : A) {
            TrieNode* node = root;
            for (char c : word) {
                if (node->children.find(c) == node->children.end()) {
                    node->children[c] = new TrieNode();
                }
                node = node->children[c];
                node->count++;
            }
        }
        // Find the shortest unique prefix for each word
        vector<string> result;
        for (const string &word : A) {
            TrieNode* node = root;
            string prefix;
            for (char c : word) {
                prefix += c;
                node = node->children[c];
                if (node->count == 1) {
                    break;
                }
            }
            result.push_back(prefix);
        }
        return result;
    }
};
```

## Code (Java)

```java
import java.util.*;

class TrieNode {
    Map<Character, TrieNode> children;
    int count;
    TrieNode() {
        children = new HashMap<>();
        count = 0;
    }
}

public class Solution {
    public ArrayList<String> prefix(ArrayList<String> A) {
        TrieNode root = new TrieNode();
        // Insert all words into the trie
        for (String word : A) {
            TrieNode node = root;
            for (int i = 0; i < word.length(); i++) {
                char c = word.charAt(i);
                if (!node.children.containsKey(c)) {
                    node.children.put(c, new TrieNode());
                }
                node = node.children.get(c);
                node.count++;
            }
        }
        // Find the shortest unique prefix for each word
        ArrayList<String> result = new ArrayList<>();
        for (String word : A) {
            TrieNode node = root;
            StringBuilder prefix = new StringBuilder();
            for (int i = 0; i < word.length(); i++) {
                char c = word.charAt(i);
                prefix.append(c);
                node = node.children.get(c);
                if (node.count == 1) {
                    break;
                }
            }
            result.add(prefix.toString());
        }
        return result;
    }
}
```

## Code (Python)

```python
class TrieNode:
    def __init__(self):
        self.children = {}
        self.count = 0

class Solution:
    # @param A : list of strings
    # @return a list of strings
    def prefix(self, A):
        root = TrieNode()
        # Insert all words into the trie
        for word in A:
            node = root
            for char in word:
                if char not in node.children:
                    node.children[char] = TrieNode()
                node = node.children[char]
                node.count += 1
        # Find the shortest unique prefix for each word
        result = []
        for word in A:
            node = root
            prefix = []
            for char in word:
                prefix.append(char)
                node = node.children[char]
                if node.count == 1:
                    break
            result.append(''.join(prefix))
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
