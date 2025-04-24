--- ❤️ ---

# 🚀 _Day 114. An Increment Problem_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/an-increment-problem/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
vector<int> Solution::solve(vector<int> &A) {
    vector<int> res;
    for(int i=0;i<A.size();i++) {
        auto it=find(res.begin(),res.end(),A[i]);
        if(it!=res.end()) {
            (*it)++;
            res.push_back(A[i]);
        }
        else {
            res.push_back(A[i]);
        }
    }
    return res;
}

```

## Code (Java)

```java
public class Solution {
     public int[] solve(int[] A) {
        HashMap<Integer,Integer> map=new HashMap<>();
        for(int i=0;i<A.length;i++){
  //          System.out.println(map);
            if(map.containsKey(A[i])) {
                int index = map.get(A[i]);
                A[index]=A[index]+1;
                if(map.containsKey(A[index])) {
                    if(index<map.get(A[index])) {
                        map.put(A[index],index);
                    }
                    map.put(A[i],i);
                }else {
                    setMap(map,index,i,A);
                    map.put(A[index],index);
                }
            }else {
                map.put(A[i],i);
            }
        }
        return A;
    }
    private void setMap(HashMap<Integer, Integer> map, int index, int k, int[] A) {
          for(int i=index;i<k;i++){
                if(A[k]==A[i]) {
                     map.put(A[i],i);
                     return;
                }
          }
    }
}


```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return a list of integers
    
    def solve(self, A):
        import heapq

        occurence_index = {}
        final = []
        for i, a in enumerate(A):
            oi = occurence_index.setdefault(a, [])
            heapq.heappush(oi, i) 
            occurence_index[a] = oi
            final.append(a)
            
            if len(oi) > 1:
                idx_to_change = heapq.heappop(oi)
                final[idx_to_change] += 1
                heapq.heappush(occurence_index.setdefault(final[idx_to_change], []), idx_to_change)
        return final

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
