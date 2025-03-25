--- ❤️ ---

# 🚀 _Day 84. Check if Grid can be Cut into Sections_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/check-if-grid-can-be-cut-into-sections/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
    #define pii pair<int,int>

    bool countLineIntersections(vector<pii>& coordinates){
        int lines = 0;
        int overlap = 0;
        for(int i=0;i<coordinates.size();++i){
            if(coordinates[i].second==0)    overlap--;
            else                            overlap++;
            if(overlap==0)
                lines++;
        }
        return lines>=3;
    }
public:
    bool checkValidCuts(int n, vector<vector<int>>& rectangles) {
        vector<pii> y_cordinates,x_cordinates;
        for(auto& rectangle: rectangles){
            y_cordinates.push_back(make_pair(rectangle[1],1));
            y_cordinates.push_back(make_pair(rectangle[3],0));
            x_cordinates.push_back(make_pair(rectangle[0],1));
            x_cordinates.push_back(make_pair(rectangle[2],0));
        }
        sort(y_cordinates.begin(),y_cordinates.end());
        sort(x_cordinates.begin(),x_cordinates.end());

        //Line-Sweep on x and y cordinates
        return (countLineIntersections(y_cordinates) or countLineIntersections(x_cordinates));
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    static class Pair {
        int first, second;
        Pair(int first, int second) {
            this.first = first;
            this.second = second;
        }
    }

    private boolean countLineIntersections(List<Pair> coordinates) {
        int lines = 0;
        int overlap = 0;
        for (Pair coord : coordinates) {
            if (coord.second == 0) overlap--;
            else overlap++;
            if (overlap == 0) lines++;
        }
        return lines >= 3;
    }

    public boolean checkValidCuts(int n, int[][] rectangles) {
        List<Pair> yCoordinates = new ArrayList<>();
        List<Pair> xCoordinates = new ArrayList<>();

        for (int[] rectangle : rectangles) {
            yCoordinates.add(new Pair(rectangle[1], 1));
            yCoordinates.add(new Pair(rectangle[3], 0));
            xCoordinates.add(new Pair(rectangle[0], 1));
            xCoordinates.add(new Pair(rectangle[2], 0));
        }

        // Sort by the first element of the pair
        yCoordinates.sort((a, b) -> Integer.compare(a.first, b.first));
        xCoordinates.sort((a, b) -> Integer.compare(a.first, b.first));

        // Line-Sweep on x and y coordinates
        return countLineIntersections(yCoordinates) || countLineIntersections(xCoordinates);
    }
}
```

## Code (Python)

```python
from typing import List

class Solution:
    def countLineIntersections(self, coordinates: List[tuple]) -> bool:
        lines = 0
        overlap = 0
        for coord in coordinates:
            if coord[1] == 0:
                overlap -= 1
            else:
                overlap += 1
            if overlap == 0:
                lines += 1
        return lines >= 3

    def checkValidCuts(self, n: int, rectangles: List[List[int]]) -> bool:
        y_coordinates = []
        x_coordinates = []

        for rectangle in rectangles:
            y_coordinates.append((rectangle[1], 1))
            y_coordinates.append((rectangle[3], 0))
            x_coordinates.append((rectangle[0], 1))
            x_coordinates.append((rectangle[2], 0))

        # Sort by the first element of the tuple
        y_coordinates.sort()
        x_coordinates.sort()

        # Line-Sweep on x and y coordinates
        return self.countLineIntersections(y_coordinates) or self.countLineIntersections(x_coordinates)
    */
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
