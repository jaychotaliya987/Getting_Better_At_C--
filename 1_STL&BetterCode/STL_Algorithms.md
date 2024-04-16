# STL Algorithms

- raising the level of abstraction.
- avoids common mistakes.
    - empty loops iterations (**UB**)
    - out of bound for loops (**UB**)
    - naive Complexity
- Used By lot of people
    - A common vocabulary
    - better then implementing yourself
    - irrelevant to your compiler

## Province of Heap 
Heap is a data structure that have the parent data that is bigger and node that is smaller at the bottom called child. can have many levels. We use heap because we can access the max of the data easily.

### Algorithms on heap

- Make heap from a data structure that has begin and end (**iterator**)
```cpp 
    std::make_heap(begin(a),end(a));
```

- Add number to heap. Not easy because we have to push the number added to the end to the parent number till we can't as parent > child.

```cpp 
    std::push_heap(begin(a),end(a));
```
- similarly we can remove the biggest element from the heap.

```cpp 
    std::pop_heap(begin(a),end(a)); // move the first element to the last and make the iterator based data structure a heap again
    std::pop_back(begin(a),end(a)); // remove the last element, first element of heap in this case.
```

- We can omit the `pop_back()` and just use `std::pop_heap()` to sort the heap. same thing is achieved by the `sort_heap`
```cpp 
    std::sort_heap(begin(a),end(a));
```

## Shores of sorting

- to sort any sortable STL container.
```cpp 
    std::sort(begin(a),end(a));
```

- To sort beginning of the container.
```cpp 
    std::partial_sort(begin(a),end(a), x); //sort till x
```
- sorts the position of the single element and leaves everything below unordered but less and above unordered but higher
```cpp 
    std::nth_element(begin(a),end(a), x); //sort x
```
- sort two merged sorted container
```cpp 
    std::inplace_merge(begin(a),end(a), x); //sort x
```