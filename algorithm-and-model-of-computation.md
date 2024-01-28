## Computational Problem:
```
A set of possible inputs and outputs for which there is a binary relationship between the domains of inputs and outputs, typically defined in terms of predicates that allow for determination of correctness of a relatinoship between an input and output.
```

## Algorithm:
```
A function which takes in inputs and maps to a correct outputs for a defined domain. Algorithms should be a fixed-sized solution to an arbitrarily large input.
```

Inductive proof is used to prove algorithmic correctness. Inductive proof requires:
- base case
- hypothesis of something to maintain
- inductive step (small value + inductive hypothesis -> apply to larger well-ordered set)

## Inductive Proof

For the example of checking if any two people in a set share a birthday:

Inductive hypothesis: if first `k` people contain match, return match before interviewing `k+1`
Base case: start with `k` = 0, return none
Assume inductive hypothesis true for `k` = `k'`, two cases:
- If `k'` contains a match, already returned a match by induction
- Else if `k'+1` contains match, check `k'` against all in in `k`



## Word Model of Computation

Data is stored at memory addresses (a.k.a words) which must be addressed within a memory address (32-bit -> 4GB, 64-bit -> 20EXB).

Operations can be integer arithmetic, logical operations, bitwise operations, and constant time read/write.