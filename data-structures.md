## Interface Definition

Specification defining
- What data you can store
- What operations can be done to the data (what they mean)

Equivalent of the problem statement.

## Data Structure

Representation defining
- How data is stored
- Algorithms for how to support operations

Equivalent to algorithmic solutions to the problem.

## Interfaces

### Set

Store N values and be able to search for a single value (a.k.a key).

### Sequence

Store N values in a particular sequence defined by the user.

#### Static

Number of items in set does not change.

`n` items: $x_0, x_1, x_2, ... , x_{n-1}$

Operations
- `build(x)`: make new data structure for items in `x`
- `len()`: return `n`
- `iter_seq()`: output $x_1, x_2, ... , x_{n-1}$ in sequence order
- `get_at(i)`: return $x_i$
- `set_at(i)`: set $x_i$ to $x$
- `get_first/last()` get first/last value $x_{n-1}
- `set_first/last(x)`: set first/last value to $x$

#### Dynamic

Number of items in set _can_ change.

Static sequence plus:
- `insert_at(i,x)`: make $x$ the new $x_i$, shifting $x_i -> x_{i+1}$, $x_{i+1} -> x_{i+2}$, $x_{n-1} -> x_{n'-1}$
- `delete_at(i)`: remove $x_i$ and shift all remaining values to the left
- `insert/delete_first/last(x)/()`

On a static array, insert/delete anywhere costs $theta_n$ time. For elements before the end, array/index shifting requires $theta_n$. At the end, memory shifting requires $theta_n$ for copy. Just to insert/delete requries a complete copy.

On a linked list, insert/delete at the front is constant time, because you can memory allocate a new node, set its value, and set the head pointer to the new node's address.

## Data Structure Approaches

### Word-RAM Model of Computation

Memory is an array of `w`-bit words. Memory can be accessed randomly.

### Arrays

Natural solution to the static sequence interface.

"Array" means a consecutive chunk of memory. Accessing `array[i]` = `memory[address(array) + i]`. This means that array access is constant time (get, set). This assumes `w` >= `lg(n)` (we need enough word-size to address the array).

Length is also constant time.

Build and iterate take linear time for read/write.

Memory allocation model:
- allocate array of size $n$ in $theta(n)$ time
- space = `O(time)`

### Linked List

Natural solution to dynamic sequence interface.

Set of nodes with [item, next] where item has value and next contains memory address to next node.

Memory allocation model:
- head (first node)
- length