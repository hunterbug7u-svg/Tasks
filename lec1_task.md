1. Which of the following is NOT a characteristic of an algorithm? Runs for an infinite time

2. An algorithm is correct if:? for every input instance it halts with the correct output

3. To make an algorithm run in less time, we typically need:? more memory

4. Pseudocode is useful because it:? describes an algorithm without language syntax

5. The best case of insertion sort occurs when the input is:? already sorted
The worst-case time complexity of insertion sort is:? O(n²)


## Project Insertion Sort

```python
A = [5, 2, 9, 1, 7]

def insertion_sort(arr):
    n = len(arr)
    for i in range(1, n):
        key = arr[i]
        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
    return arr

sorted_A = insertion_sort(A.copy())
print(f"Original array: {A}")
print(f"Sorted array: {sorted_A}")
```