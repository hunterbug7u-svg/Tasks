1. LEFT(i) in a 1-based heap is…?  B: LEFT(i) = 2i

2. BUILD-MAX-HEAP runs in…?  B: O(n)

3. Is heap sort stable? B: no, equal keys can change order

4. Extra space of heap sort (iterative)? A: O(1) when heapify is iterative

5. Build? `[9, 4, 5, 1, 3, 2]`

6. Trace? `After iteration 1: [14, 8, 10, 4, 7, 9, 3, 2, 1, 16] (heap size 9); after iteration 2: [10, 8, 9, 4, 7, 1, 3, 2, 14, 16] (heap size 8)`

7. Insert? `[16, 15, 10, 14, 7, 9, 3, 8]`

8. Think? MAX-HEAPIFY needs both subtrees to be heaps. Leaves already are, so going bottom-up from ⌊n/2⌋ guarantees this at every step.