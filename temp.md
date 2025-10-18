```python
def insertion_sort_basic(arr):
    # Start from the second element (index 1)
    for i in range(1, len(arr)):
        key = arr[i]  # Element to be inserted
        j = i - 1     # Index of last element in sorted portion
        
        # Shift elements greater than key one position to the right
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        
        # Insert the key at its correct position
        arr[j + 1] = key
    
    return arr

# Example
nums = [64, 34, 25, 12, 22, 11, 90]
print(insertion_sort_basic(nums))  # Output: [11, 12, 22, 25, 34, 64, 90]
```
