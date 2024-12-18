## Problem
Given an integer n, return a counter function. This counter function initially returns n and then returns 1 more than the previous value every subsequent time it is called (n, n + 1, n + 2, etc).

#### Examples
| Input | Output | Explanation |
|---|---|---|
| n = 10 | [10,11,12] |  counter() = 10 // The first time counter() is called, it returns n. counter() = 11 // Returns 1 more than the previous time. counter() = 12 // Returns 1 more than the previous time. |
| n = -2 | [-2,-1,0,1,2] | counter() initially returns -2. Then increases after each sebsequent call. |
 
#### Constraints:
- -1000 <= n <= 1000
- 0 <= calls.length <= 1000
- calls[i] === "call"

## Solution
```ts
function createCounter(n: number): () => number {
    let i = n;
    return () => i++;
}


/** 
 * const counter = createCounter(10)
 * counter() // 10
 * counter() // 11
 * counter() // 12
 */
```
