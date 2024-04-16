## G1 - No raw loops
- Difficulty reading.
- Performance Problem.

### Alternatives to Raw Loops
- Use algorithms in STL.
- Contribute to open source library, create an algorithm.

## G2 - Use Range Library
- `find(begin(a), end(a), x)` -> `find(a,x)` 
- simplifies the code, makes it readable
- boost and ASL are good range library
- many variations of `find()` and `copy()` algorithms

## G3 - Ranged based For Loops are great
- function use can be unreadable some time. 
for example: 

```cpp
std::transform(v.begin(), v.end(), v.begin(), [](int n) { return n * n; });
```
can be simply written as
```cpp
for (const auto& e:r) f(e);
```
- Ranged for loops are great but should not be long. **keep them short**, Max 2 function calls inside the for loop.

## G4 - Use short lambdas
- long comparisons are hard to read and can be separated from the lambda body and putted into a function for readability.

## G5 - No Raw Pointer
- you need to take care of them. Creating the pointers needed to be deleted. Must free the storage
- less the readability.

## G6 - Efficiency with Algorithms, Performance with Data Structure
- Less work more efficiency, Do not waste resources doing things that are not supposed to be done.
- Data Structures gives the performance, Linked list is slower then vector in almost all the tasks.
- Use contiguous, dense data structures. That promotes usage of L1, L2 and L3 caches. Caches are faster than main memory.