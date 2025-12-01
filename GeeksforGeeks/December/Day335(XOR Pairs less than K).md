--- ❤️ ---

# 🚀 _Day 335. XOR Pairs less than K_ 🧠


The problem can be found at the following link: [Problem Link]()

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    struct Node {
        int cnt;
        Node* child[2];
        Node() {
            cnt = 0;
            child[0] = child[1] = nullptr;
        }
    };

    Node* root;
    
    // Insert number into Trie
    void insert(int x) {
        Node* cur = root;
        for (int i = 15; i >= 0; i--) {          // since arr[i] <= 50000 < 2^16
            int bit = (x >> i) & 1;
            if (!cur->child[bit])
                cur->child[bit] = new Node();
            cur = cur->child[bit];
            cur->cnt++;
        }
    }
    
    // Count numbers already in Trie such that (x ^ y) < k
    int countLess(int x, int k) {
        Node* cur = root;
        int ans = 0;
        
        for (int i = 15; i >= 0; i--) {
            if (!cur) break;
            
            int xb = (x >> i) & 1;
            int kb = (k >> i) & 1;
            
            if (kb == 1) {
                // case 1: xor bit = 0 → means ybit = xb
                if (cur->child[xb])
                    ans += cur->child[xb]->cnt;
                
                // go to other side for further search
                cur = cur->child[1 - xb];
            } 
            else {
                // kb == 0
                // xor bit must be 0 → ybit = xb
                cur = cur->child[xb];
            }
        }
        return ans;
    }

    int cntPairs(vector<int>& arr, int k) {
        root = new Node();
        int ans = 0;
        
        for (int x : arr) {
            ans += countLess(x, k);
            insert(x);
        }
        return ans;
    }
};

```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
