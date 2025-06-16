--- ❤️ ---

# 🚀 _Day 167. Word Ladder I_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/word-ladder-i/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>
#include <unordered_set>
#include <queue>
using namespace std;

class Solution {
public:
    int solve(string A, string B, vector<string>& C) {
        if (A == B) return 1;
        
        unordered_set<string> wordSet(C.begin(), C.end());
        if (wordSet.find(B) == wordSet.end()) return 0;
        
        queue<pair<string, int>> q;
        q.push({A, 1});
        unordered_set<string> visited;
        visited.insert(A);
        
        while (!q.empty()) {
            auto current = q.front();
            q.pop();
            string currentWord = current.first;
            int steps = current.second;
            
            for (int i = 0; i < currentWord.size(); ++i) {
                char originalChar = currentWord[i];
                for (char c = 'a'; c <= 'z'; ++c) {
                    if (c == originalChar) continue;
                    string newWord = currentWord;
                    newWord[i] = c;
                    if (newWord == B) return steps + 1;
                    if (wordSet.find(newWord) != wordSet.end() && visited.find(newWord) == visited.end()) {
                        visited.insert(newWord);
                        q.push({newWord, steps + 1});
                    }
                }
            }
        }
        
        return 0;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(String A, String B, ArrayList<String> C) {
        if (A.equals(B)) return 1;
        
        Set<String> wordSet = new HashSet<>(C);
        if (!wordSet.contains(B)) return 0;
        
        Queue<Pair<String, Integer>> queue = new LinkedList<>();
        queue.add(new Pair<>(A, 1));
        Set<String> visited = new HashSet<>();
        visited.add(A);
        
        while (!queue.isEmpty()) {
            Pair<String, Integer> current = queue.poll();
            String currentWord = current.getKey();
            int steps = current.getValue();
            
            for (int i = 0; i < currentWord.length(); i++) {
                char[] wordArray = currentWord.toCharArray();
                for (char c = 'a'; c <= 'z'; c++) {
                    if (c == wordArray[i]) continue;
                    wordArray[i] = c;
                    String newWord = new String(wordArray);
                    if (newWord.equals(B)) return steps + 1;
                    if (wordSet.contains(newWord) && !visited.contains(newWord)) {
                        visited.add(newWord);
                        queue.add(new Pair<>(newWord, steps + 1));
                    }
                }
            }
        }
        
        return 0;
    }
    
    static class Pair<K, V> {
        private K key;
        private V value;
        
        public Pair(K key, V value) {
            this.key = key;
            this.value = value;
        }
        
        public K getKey() {
            return key;
        }
        
        public V getValue() {
            return value;
        }
    }
}
```

## Code (Python)

```python
from collections import deque

class Solution:
    # @param A : string
    # @param B : string
    # @param C : list of strings
    # @return an integer
    def solve(self, A, B, C):
        if A == B:
            return 1
        
        word_set = set(C)
        if B not in word_set:
            return 0
        
        queue = deque()
        queue.append((A, 1))
        visited = set()
        visited.add(A)
        
        while queue:
            current_word, steps = queue.popleft()
            
            for i in range(len(current_word)):
                for c in 'abcdefghijklmnopqrstuvwxyz':
                    if c == current_word[i]:
                        continue
                    new_word = current_word[:i] + c + current_word[i+1:]
                    if new_word == B:
                        return steps + 1
                    if new_word in word_set and new_word not in visited:
                        visited.add(new_word)
                        queue.append((new_word, steps + 1))
        
        return 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
