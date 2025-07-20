--- ❤️ ---

# 🚀 _Day 201. Delete Duplicate Folders in System_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/delete-duplicate-folders-in-system/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Trie {
public:
    unordered_map<string, Trie*> children;
    bool deleted = false;
};

class Solution {
public:
    vector<vector<string>> deleteDuplicateFolder(vector<vector<string>>& paths) {
        Trie* root = new Trie();

        for (auto& path : paths) {
            Trie* cur = root;
            for (auto& name : path) {
                if (cur->children.find(name) == cur->children.end()) {
                    cur->children[name] = new Trie();
                }
                cur = cur->children[name];
            }
        }

        unordered_map<string, Trie*> g;

        auto dfs = [&](this auto&& dfs, Trie* node) -> string {
            if (node->children.empty()) return "";

            vector<string> subs;
            for (auto& child : node->children) {
                subs.push_back(child.first + "(" + dfs(child.second) + ")");
            }
            sort(subs.begin(), subs.end());
            string s = "";
            for (auto& sub : subs) s += sub;

            if (g.contains(s)) {
                node->deleted = true;
                g[s]->deleted = true;
            } else {
                g[s] = node;
            }
            return s;
        };

        dfs(root);

        vector<vector<string>> ans;
        vector<string> path;

        auto dfs2 = [&](this auto&& dfs2, Trie* node) -> void {
            if (node->deleted) return;
            if (!path.empty()) {
                ans.push_back(path);
            }
            for (auto& child : node->children) {
                path.push_back(child.first);
                dfs2(child.second);
                path.pop_back();
            }
        };

        dfs2(root);

        return ans;
    }
};
```

## Code (Java)

```java
class Trie {
    Map<String, Trie> children;
    boolean deleted;

    public Trie() {
        children = new HashMap<>();
        deleted = false;
    }
}

class Solution {
    public List<List<String>> deleteDuplicateFolder(List<List<String>> paths) {
        Trie root = new Trie();
        for (List<String> path : paths) {
            Trie cur = root;
            for (String name : path) {
                if (!cur.children.containsKey(name)) {
                    cur.children.put(name, new Trie());
                }
                cur = cur.children.get(name);
            }
        }

        Map<String, Trie> g = new HashMap<>();

        var dfs = new Function<Trie, String>() {
            @Override
            public String apply(Trie node) {
                if (node.children.isEmpty()) {
                    return "";
                }
                List<String> subs = new ArrayList<>();
                for (var entry : node.children.entrySet()) {
                    subs.add(entry.getKey() + "(" + apply(entry.getValue()) + ")");
                }
                Collections.sort(subs);
                String s = String.join("", subs);
                if (g.containsKey(s)) {
                    node.deleted = true;
                    g.get(s).deleted = true;
                } else {
                    g.put(s, node);
                }
                return s;
            }
        };

        dfs.apply(root);

        List<List<String>> ans = new ArrayList<>();
        List<String> path = new ArrayList<>();

        var dfs2 = new Function<Trie, Void>() {
            @Override
            public Void apply(Trie node) {
                if (node.deleted) {
                    return null;
                }
                if (!path.isEmpty()) {
                    ans.add(new ArrayList<>(path));
                }
                for (Map.Entry<String, Trie> entry : node.children.entrySet()) {
                    path.add(entry.getKey());
                    apply(entry.getValue());
                    path.remove(path.size() - 1);
                }
                return null;
            }
        };

        dfs2.apply(root);

        return ans;
    }
}
```

## Code (Python)

```python
class Trie:
    def __init__(self):
        self.children: Dict[str, "Trie"] = defaultdict(Trie)
        self.deleted: bool = False


class Solution:
    def deleteDuplicateFolder(self, paths: List[List[str]]) -> List[List[str]]:
        root = Trie()
        for path in paths:
            cur = root
            for name in path:
                if cur.children[name] is None:
                    cur.children[name] = Trie()
                cur = cur.children[name]

        g: Dict[str, Trie] = {}

        def dfs(node: Trie) -> str:
            if not node.children:
                return ""
            subs: List[str] = []
            for name, child in node.children.items():
                subs.append(f"{name}({dfs(child)})")
            s = "".join(sorted(subs))
            if s in g:
                node.deleted = g[s].deleted = True
            else:
                g[s] = node
            return s

        def dfs2(node: Trie) -> None:
            if node.deleted:
                return
            if path:
                ans.append(path[:])
            for name, child in node.children.items():
                path.append(name)
                dfs2(child)
                path.pop()

        dfs(root)
        ans: List[List[str]] = []
        path: List[str] = []
        dfs2(root)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
