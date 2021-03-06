
# CSE 143 Exam Reminders

Kyle Yan

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
- Always check whether a stack/queue **`isEmpty()`** before `peek()`-ing/`pop()`-ping/`remove()`-ing.
- Sometimes repeated action (`while`) is needed (`if` might not be enough, see *expunge*).
- Use **Generics**! 

## Linked Lists

- **DRAW DIAGRAMS!**
- In linked lists, set the next of the last element to **null**.
- In linked lists, remember to write **`curr = curr.next;`** .
- When using `while (curr.next != null)`, remember to check **the first node**. 
- Start editing from the **previous node** of the node to change! 
- Deal with **the front node** separately (but similarly)! 

## `Set`s and `Map`s

- *Union* problem specific: go through both maps when merging. 
- Use `new HashSet<>()` or `new TreeSet<>()` (`new HashMap<>()` or `new TreeMap<>()`). Don't write `new Set<>()` (`new Map<>()`)! 
- **Use `map.keySet()` to traverse the `Map` with for-each loop. **
- Sometimes `Double`(`double`) is needed. `Integer` (`int`) might not be enough!

## `compareTo`

- Use `Integer.compare()` and `Double.compare()` to compare primitive types! Don't use subtraction. 
- Remember to add the **`private`** modifier before fields when writing a class!
- *Rational* problem specific: compare the **denominator** instead of the **numerator**, because by definition $\frac{0}{4}$ is bigger than $\frac{0}{2}$.

## Binary Search

- Binary search returns $-n-1$ if the value is not found, where $n$ is the index where the value *could* be inserted. 
- In binary search, the new region is $[front, mid-1]$ or $[mid+1, end]$,  **NOT** $[front, mid]$ or $[mid, end]$. 

## Recursion

- Take care of exceptions first! Then base cases!
- Be careful about the spaces and the commas! 
- Think about the base cases carefully. 

## Recursive Backtracking

- Analyze the sequence the answers are printed in. 
- Check boundaries - Exceed goal? 
- Consider adding helper parameters.

## Binary Trees

- Check if `overallRoot == null` when necessary! 

## Collection Mystery

- Be careful about the order of the elements! (`TreeMap`s and `TreeSet`s). 
