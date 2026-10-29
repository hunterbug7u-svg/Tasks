1. A recurrence for merge sort is…? B: T(n) = 2T(n/2) + n

2. Quicksort worst case is…? C: Θ(n²)

3. Which sort is stable? A: merge sort (quicksort is not stable)

4. Binary search needs…? B: a sorted array

5. Trace? `Halves [9,4,7] [1,6,3], then [9,4] [7], [1,6] [3]; merges give [4,9] → [4,7,9] and [1,6] → [1,3,6]; final [1,3,4,6,7,9]`

6. Partition? `Pivot 6: result [3, 2, 5, 1, 4, 6, 8, 7], q = 6`

7. Solve? Case 1: Θ(n²); with n²: case 2, Θ(n² log n)

8. Think? Quicksort puts the work in partition; merge sort puts it in merge


## Project: Sorting Benchmark Lab

```python
# sorted vs insertion vs merge
import time
a = [5, 6, 10, 13, 9, 8, 7, 7, 8, 10, 8]

def insertion(a):
    for i in range(1, len(a)):
        key, j = a[i], i - 1
        while j >= 0 and a[j] > key:
            a[j + 1] = a[j]
            j -= 1
        a[j + 1] = key
    return a

def merge_sort(a):
    if len(a) <= 1:
        return a
    mid = len(a) // 2
    L, R = merge_sort(a[:mid]), merge_sort(a[mid:])
    out, i, j = [], 0, 0
    while i < len(L) and j < len(R):
        if L[i] <= R[j]:
            out.append(L[i]); i += 1
        else:
            out.append(R[j]); j += 1
    out.extend(L[i:]); out.extend(R[j:])
    return out
    
s1 = time.perf_counter()
insertion(a)
e1 = time.perf_counter()

s2 = time.perf_counter()
merge_sort(a)
e2 = time.perf_counter()

s3 = time.perf_counter()
sorted(a)
e3 = time.perf_counter()

print("insertion : " + str((e1 - s1) * 9999))
print("merge : " + str((e2 - s2) * 9999))
print("sorted : " + str((e3 - s3) * 9999))
```