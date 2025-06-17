--- ❤️ ---

# 🚀 _Day 168. Smallest Multiple With 0 and 1_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/smallest-multiple-with-0-and-1/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
char * multiple(int A){
	int flag[A];
	int parent[A];
	int vlaue[A];
	int i = 0;
	int queue[A];
	int front = -1;
	int back = -1;
	for(i=0;i<A;i++){
		flag[i] = 0;
		parent[i] = 0;
		vlaue[i] = 0;
	}
	
	int state = 1%A;
	flag[state] = 1;
	vlaue[state] = 1;
	queue[0] = state;
	front = 0;
	back = 0;
	char *re = (char*)malloc(sizeof(char)*(A+120));
	re[0] = '\0';
		
	while(front<=back){
		state = queue[front++];
		if(state == 0)
			break;
		int newstate = (state*10)%A;
		if(flag[newstate]==0)
		{
			queue[++back] = newstate;
			flag[newstate] = 1;
			vlaue[newstate] = 0;
			parent[newstate] = state;
		}
		newstate++;
		if(newstate>=A)newstate -= A;
		if(flag[newstate]==0)
		{
			queue[++back] = newstate;
			flag[newstate] = 1;
			vlaue[newstate] = 1;
			parent[newstate] = state;
		}
	}
	int j  =0 ;
	re[j++] = vlaue[state]+'0';
    state = parent[state];
//	for(i = 0;i<55;i++)printf("%d",parent[i]);
//	printf("ewew");
	while( state != 0){
	    re[j++] = vlaue[state]+'0';
		state = parent[state];
		
	}
	re[j] = '\0';
	j--;
	for(i = 0 ;i < j ; i++, j--){
		char t = re[i];
		re[i] = re[j];
		re[j] = t;
	}
	return re;
	
}

```

## Code (Java)

```java
public class Solution {
    
    public static class Node {
        String value;
        int modN = -1;
        
        public Node(String x, int y) {
            value  = x;
            modN = y;
        }
    }
    
    public String multiple(int N) {

        ArrayDeque<Node> queue = new ArrayDeque<>();
        queue.addLast(new Node("1", 1 % N));
        
        boolean[] visited = new boolean[N];
        visited[1%N] = true;
        
        while (!queue.isEmpty()) {
            Node node = queue.pollFirst();
            
            if (node.modN == 0) {
                return node.value;
            }
            
            int s1 = (node.modN * 10) % N;
            int s2 = (node.modN * 10 + 1) % N;
                
            if (!visited[s1]) {
                queue.addLast(new Node(node.value + "0", s1));
                visited[s1] = true;
            }
            
            if (!visited[s2]) {
                queue.addLast(new Node(node.value + "1", s2));
                visited[s2] = true;
            }
            
            
        }
        
        return "";
    }
}


```

## Code (Python)

```python
from collections import deque

# Definition for a  binary tree node
class TreeNode:
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None

class Solution:
    # @param A : root node of tree
    # @return a list of list of integers
    def levelOrder(self, A):
        if not A:
            return []
        
        result = []
        queue = deque([A])
        
        while queue:
            level_size = len(queue)
            current_level = []
            
            for _ in range(level_size):
                node = queue.popleft()
                current_level.append(node.val)
                
                if node.left:
                    queue.append(node.left)
                if node.right:
                    queue.append(node.right)
            
            result.append(current_level)
        
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
