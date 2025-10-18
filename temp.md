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
I'll break this down step-by-step so you can understand it perfectly for your exam! 

## **The Big Picture**

Imagine you're sorting playing cards in your hand:
- You pick up one card at a time
- You insert it into the correct position among the cards you're already holding
- That's exactly what insertion sort does!

---

## **Line-by-Line Explanation**

```python
def insertion_sort_basic(arr):
    for i in range(1, len(arr)):
```
- **Start from index 1** (second element), not 0
- **Why?** We assume the first element is already "sorted" by itself

```python
        key = arr[i]
```
- **key** = the element we want to insert into the sorted part
- Think: "This is the card I just picked up"

```python
        j = i - 1
```
- **j** points to the last element in the sorted part
- We'll use `j` to move backwards through sorted elements

```python
        while j >= 0 and arr[j] > key:
```
- **Two conditions to keep looping:**
  1. `j >= 0` → Haven't reached the start of array
  2. `arr[j] > key` → Current element is bigger than our key

```python
            arr[j + 1] = arr[j]
```
- **Shift the bigger element one position to the right**
- This creates space for our `key`

```python
            j -= 1
```
- **Move backwards** to check the next element

```python
        arr[j + 1] = key
```
- **Insert the key** in the empty spot we created
- Why `j + 1`? Because we decreased `j` one time too many in the loop

---

## **Detailed Walkthrough with `[64, 34, 25]`**

### **Initial State:**
```
[64, 34, 25]
 ↑
sorted part (just one element)
```

### **Pass 1: i=1, key=34**
```
[64, 34, 25]
     ↑
   key=34

Compare: Is 64 > 34? YES
Shift 64 right: [64, 64, 25]
Insert 34: [34, 64, 25]
```

### **Pass 2: i=2, key=25**
```
[34, 64, 25]
         ↑
       key=25

Compare: Is 64 > 25? YES → Shift right
[34, 64, 64]

Compare: Is 34 > 25? YES → Shift right
[34, 34, 64]

Insert 25: [25, 34, 64] ✓ SORTED!
```

---

## **Key Points for Your Exam**

### **1. Time Complexity**
- **Best Case: O(n)** → Array already sorted, just scan through
- **Worst Case: O(n²)** → Array reversed, maximum shifts
- **Average Case: O(n²)**

### **2. Space Complexity**
- **O(1)** → Only uses a few variables (key, i, j), no extra arrays

### **3. Properties**
- ✅ **Stable** → Equal elements keep their original order
- ✅ **In-place** → Sorts within the original array
- ✅ **Adaptive** → Fast on nearly-sorted data
- ✅ **Online** → Can sort data as it arrives

### **4. When to Use?**
- Small datasets (< 50 elements)
- Nearly sorted data
- When stability matters
- When simplicity matters

---

## **Common Exam Questions**

**Q: Why start from index 1, not 0?**  
A: We consider the first element already sorted (a single element is always sorted).

**Q: What does the while loop do?**  
A: It shifts all elements greater than `key` one position to the right, creating space for the key.

**Q: Is it stable?**  
A: Yes! Equal elements maintain their relative order because we only shift when `arr[j] > key` (not `>=`).

**Q: Trace the algorithm on [5, 2, 4, 1]**

```
Start: [5, 2, 4, 1]

i=1, key=2: [2, 5, 4, 1]
i=2, key=4: [2, 4, 5, 1]
i=3, key=1: [1, 2, 4, 5] ✓
```

---

## **Quick Memory Trick**

Think: **"Pick, Compare, Shift, Insert"**
1. **Pick** the next element (key)
2. **Compare** with sorted elements (going backwards)
3. **Shift** bigger elements to the right
4. **Insert** key in the empty spot

---

Good luck on your exam tomorrow! Practice tracing through a small example by hand—that's the best way to cement your understanding. 🎯
