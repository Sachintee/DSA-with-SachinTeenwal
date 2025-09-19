--- ❤️ ---

# 🚀 _Day 262. Design Spreadsheet_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/design-spreadsheet)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Spreadsheet {
private:
    unordered_map<string, int> d;

public:
    Spreadsheet(int rows) {}

    void setCell(string cell, int value) {
        d[cell] = value;
    }

    void resetCell(string cell) {
        d.erase(cell);
    }

    int getValue(string formula) {
        int ans = 0;
        stringstream ss(formula.substr(1));
        string cell;
        while (getline(ss, cell, '+')) {
            if (isdigit(cell[0])) {
                ans += stoi(cell);
            } else {
                ans += d.count(cell) ? d[cell] : 0;
            }
        }
        return ans;
    }
};

/**
 * Your Spreadsheet object will be instantiated and called as such:
 * Spreadsheet* obj = new Spreadsheet(rows);
 * obj->setCell(cell,value);
 * obj->resetCell(cell);
 * int param_3 = obj->getValue(formula);
 */
```

## Code (Java)

```java
class Spreadsheet {
    private Map<String, Integer> d = new HashMap<>();

    public Spreadsheet(int rows) {
    }

    public void setCell(String cell, int value) {
        d.put(cell, value);
    }

    public void resetCell(String cell) {
        d.remove(cell);
    }

    public int getValue(String formula) {
        int ans = 0;
        for (String cell : formula.substring(1).split("\\+")) {
            ans += Character.isDigit(cell.charAt(0)) ? Integer.parseInt(cell)
                                                     : d.getOrDefault(cell, 0);
        }
        return ans;
    }
}

/**
 * Your Spreadsheet object will be instantiated and called as such:
 * Spreadsheet obj = new Spreadsheet(rows);
 * obj.setCell(cell,value);
 * obj.resetCell(cell);
 * int param_3 = obj.getValue(formula);
 */
```

## Code (Python)

```python
class Spreadsheet:

    def __init__(self, rows: int):
        self.d = {}

    def setCell(self, cell: str, value: int) -> None:
        self.d[cell] = value

    def resetCell(self, cell: str) -> None:
        self.d.pop(cell, None)

    def getValue(self, formula: str) -> int:
        ans = 0
        for cell in formula[1:].split("+"):
            ans += int(cell) if cell[0].isdigit() else self.d.get(cell, 0)
        return ans


# Your Spreadsheet object will be instantiated and called as such:
# obj = Spreadsheet(rows)
# obj.setCell(cell,value)
# obj.resetCell(cell)
# param_3 = obj.getValue(formula)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
