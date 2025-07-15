--- ❤️ ---

# 🚀 _Day 196. Dictionary in C#_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/dictionary-in-c/)

## 🎯 **My Approach:**


## Code(C#)
```c#
using System;
using System.IO;
using System.Collections.Generic;

class MAIN {
    public static void Main(string[] args) {
        int[] A = new int[10];
        for (int i = 0; i < 10; i++)
            A[i] = Convert.ToInt32(Console.ReadLine());

        // Declare a dictionary of integer type
        Dictionary<int, int> freq = new Dictionary<int, int>();

        // Count the frequency of all the elements
        foreach (int num in A) {
            if (freq.ContainsKey(num))
                freq[num]++;
            else
                freq[num] = 1;
        }

        // Print the element with the largest frequency
        int maxFreq = -1;
        int maxElem = -1;

        foreach (var kvp in freq) {
            if (kvp.Value > maxFreq) {
                maxFreq = kvp.Value;
                maxElem = kvp.Key;
            }
        }

        Console.WriteLine(maxElem);

        // Print the smallest element in the array
        int smallest = int.MaxValue;
        foreach (int num in A) {
            if (num < smallest)
                smallest = num;
        }

        Console.WriteLine(smallest);

        // Print the values present in the dictionary separated by a space
        foreach (var kvp in freq) {
            Console.Write(kvp.Value + " ");
        }
        Console.WriteLine();
    }
}

```

## Code (Java)

```java
import java.util.*;

class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int[] A = new int[10];
        for (int i = 0; i < 10; i++)
            A[i] = sc.nextInt();

        // Declare a dictionary using HashMap
        HashMap<Integer, Integer> freq = new HashMap<>();

        // Count the frequency of all elements
        for (int num : A) {
            freq.put(num, freq.getOrDefault(num, 0) + 1);
        }

        // Print the element with the largest frequency
        int maxFreq = -1;
        int maxElem = -1;
        for (Map.Entry<Integer, Integer> entry : freq.entrySet()) {
            if (entry.getValue() > maxFreq) {
                maxFreq = entry.getValue();
                maxElem = entry.getKey();
            }
        }
        System.out.println(maxElem);

        // Print the smallest element in the array
        int smallest = Integer.MAX_VALUE;
        for (int num : A) {
            if (num < smallest)
                smallest = num;
        }
        System.out.println(smallest);

        // Print the values present in the dictionary separated by a space
        for (int value : freq.values()) {
            System.out.print(value + " ");
        }
        System.out.println();
    }
}

```

## Code (Python)

```python
def main():
    A = []
    for _ in range(10):
        A.append(int(input()))
    
    freq = {}
    for num in A:
        if num in freq:
            freq[num] += 1
        else:
            freq[num] = 1

    # Print the element with the largest frequency
    maxElem = max(freq, key=lambda k: freq[k])
    print(maxElem)

    # Print the smallest element in the array
    smallest = min(A)
    print(smallest)

    # Print the values present in the dictionary separated by a space
    for value in freq.values():
        print(value, end=' ')
    print()

if __name__ == "__main__":
    main()

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
