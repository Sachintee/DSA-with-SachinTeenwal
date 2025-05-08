--- ❤️ ---

# 🚀 _Day 128. Hotel Reviews_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/hotel-reviews/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>
#include <unordered_set>
#include <algorithm>

using namespace std;

class Solution {
public:
    vector<int> solve(string A, vector<string> B) {
        unordered_set<string> goodWords;
        size_t start = 0;
        size_t end = A.find('_');
        while (end != string::npos) {
            goodWords.insert(A.substr(start, end - start));
            start = end + 1;
            end = A.find('_', start);
        }
        goodWords.insert(A.substr(start));
        
        vector<pair<int, int>> reviewsWithIndices;
        for (int i = 0; i < B.size(); ++i) {
            const string& review = B[i];
            start = 0;
            end = review.find('_');
            int count = 0;
            while (end != string::npos) {
                string word = review.substr(start, end - start);
                if (goodWords.find(word) != goodWords.end()) {
                    count++;
                }
                start = end + 1;
                end = review.find('_', start);
            }
            string word = review.substr(start);
            if (goodWords.find(word) != goodWords.end()) {
                count++;
            }
            reviewsWithIndices.emplace_back(-count, i);
        }
        
        sort(reviewsWithIndices.begin(), reviewsWithIndices.end());
        
        vector<int> result;
        for (const auto& entry : reviewsWithIndices) {
            result.push_back(entry.second);
        }
        return result;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public ArrayList<Integer> solve(String A, ArrayList<String> B) {
        Set<String> goodWords = new HashSet<>();
        String[] goodWordsArray = A.split("_");
        for (String word : goodWordsArray) {
            goodWords.add(word);
        }
        
        List<Pair<Integer, Integer>> reviewsWithIndices = new ArrayList<>();
        for (int i = 0; i < B.size(); i++) {
            String review = B.get(i);
            String[] words = review.split("_");
            int count = 0;
            for (String word : words) {
                if (goodWords.contains(word)) {
                    count++;
                }
            }
            reviewsWithIndices.add(new Pair<>(-count, i));
        }
        
        Collections.sort(reviewsWithIndices, new Comparator<Pair<Integer, Integer>>() {
            @Override
            public int compare(Pair<Integer, Integer> a, Pair<Integer, Integer> b) {
                return a.getKey().compareTo(b.getKey());
            }
        });
        
        ArrayList<Integer> result = new ArrayList<>();
        for (Pair<Integer, Integer> entry : reviewsWithIndices) {
            result.add(entry.getValue());
        }
        return result;
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
class Solution:
    # @param A : string
    # @param B : list of strings
    # @return a list of integers
    def solve(self, A, B):
        good_words = set(A.split('_'))
        reviews_with_indices = []
        
        for index, review in enumerate(B):
            words = review.split('_')
            count = 0
            for word in words:
                if word in good_words:
                    count += 1
            reviews_with_indices.append((-count, index))  # Using negative for ascending sort
        
        reviews_with_indices.sort()
        result = [idx for (neg_count, idx) in reviews_with_indices]
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
