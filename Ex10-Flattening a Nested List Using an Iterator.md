# Flattening a Nested List Using an Iterator
## DATE:18-09-2025
## AIM:
To design and implement a class NestedIterator that flattens a nested list of integers such that all integers can be accessed sequentially using an iterator interface (next() and hasNext()).
## Algorithm
1. Start the program.    
2. Define an interface-like class `NestedInteger` that can represent either a single integer or a nested list.    
3. Use a stack or recursion to flatten all integers from the nested list into a single list.    
4. Store the flattened list and maintain an index to track the current element.    
5. Implement `next()` to return the next integer and `hasNext()` to check if more integers exist.    
6. Test the iterator with a sample nested list.    
7. Stop the program.     

## Program:
```java
/*
Program to find Flattening a Nested List Using an Iterator
Developed by: K L RAVEENDRANATH
RegisterNumber:  212224060212
*/

import java.util.*;

public class FlattenNestedListSimple {
    public static List<Integer> flattenList(List<Object> nestedList) {
        List<Integer> result = new ArrayList<>();
        for (Object element : nestedList) {
            if (element instanceof Integer) {
                result.add((Integer) element);
            } else if (element instanceof List) {
                result.addAll(flattenList((List<Object>) element));
            }
        }
        return result;
    }

    public static void main(String[] args) {
        // Example nested list: [1, [2, [3, 4], 5]]
        List<Object> nestedList = new ArrayList<>();
        nestedList.add(1);
        nestedList.add(Arrays.asList(2, Arrays.asList(3, 4), 5));

        System.out.println("Original Nested List: " + nestedList);

        List<Integer> flattened = flattenList(nestedList);

        System.out.println("Flattened List: " + flattened);
    }
}
```

## Output:
<img width="862" height="149" alt="image" src="https://github.com/user-attachments/assets/0d9d4451-f2e3-4488-b1ae-accad45d72ef" />


## Result:
The NestedIterator class successfully flattens a nested list of integers into a single list and provides sequential access using standard iterator methods.
