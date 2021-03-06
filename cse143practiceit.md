
# CSE 143 Mid-term Reminders

## General 

- Check **`=`** signs (`<` vs `<=`, `>` vs `>=`).
- Check edge cases: **0**, negative values, empty data structure, etc.
- Throw Exceptions when needed. 
- Always debug the code by hand!
- **Be careful when `toLowerCase` should be called.**
- Add `()` for methods; don't for fields. 
- Add parentheses for ternary expressions! `return (a%10==b%10?1:0) + digitMatch(a/10, b/10);`
- **Read through the spec carefully.**
 

## `ArrayList`s

- When doing *"ArrayListMystery"*, be careful that the indices are changing. 

## `Stack`s and `Queue`s

- **DRAW DIAGRAMS!**
- Always check whether a stack/queue **is empty** before peeking/popping/"element-ing"/removing.
- Sometimes repeated action (`while`) is needed (`if` might not be enough, see *expunge*).
- Use **Generics**! 

## Linked Lists

- **DRAW DIAGRAMS!**
- In linked lists, set the next of the last element to **null**.
- In linked lists, remember to write **`curr = curr.next;`** .
- When using `while (curr.next != null)`, remember to check **the first node**. 

## `Set`s and `Map`s

- *Union* problem specific: go through both maps when merging. 
- Use `new HashSet<>()` or `new TreeSet<>()` (`new HashMap<>()` or `new TreeMap<>()`). Don't write `new Set<>()` (`new Map<>()`)! 
- **Use `map.keySet()` to traverse the `Map` with for-each loop. **
- Sometimes `Double`(`double`) is needed. `Integer` (`int`) might not be enough!

## `compareTo`

- Only return `int` value for the `compareTo` function. 
- *Rational* problem specific: compare the **denominator** instead of the **numerator**, because by definition $\frac{0}{4}$ is bigger than $\frac{0}{2}$.

## Binary Search

- Binary search returns $-n-1$ if the value is not found, where $n$ is the index where the value *could* be inserted. 
- In binary search, the new region is $[front, mid-1]$ or $[mid+1, end]$,  **NOT** $[front, mid]$ or $[mid, end]$. 

## Recursion

- Take care of exceptions first!
- Be careful about the spaces and the commas! 
- Think about the base cases carefully. 

## Recursive Backtracking

- Analyze the sequence the answers are printed in. 
- Check boundaries - Exceed goal? 
- Consider adding helper parameters.
