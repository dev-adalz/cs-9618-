##QUestions
# **20 Practice Questions for Your Exam**

---

## **SEARCHING (Questions 1-4)**

### **1. Linear Search**
Write a function to find the position of element 25 in the list `[10, 5, 25, 30, 15]`. If not found, return -1.
## Answer:
```python
def lin_search(arr,item):
    for i in range(len(arr)):
        if arr[i]==item:
            flag=True
            break
        else:
            flag=False
    if flag==True:
        return 'found'
    else:
        return -1
```

### **2. Binary Search**
Given a sorted list `[2, 5, 8, 12, 16, 23, 38, 45, 56, 67, 78]`, write a binary search function to find element 23. Show all steps.
## Answer:
```python
def b_search(arr,key):
    left=0
    right=len(arr)-1
    while left<=right:
        flag=False
        mid = (left+right)//2
        if key == arr[mid]:
            flag=True
            break
        elif arr[mid]<key:
            left=mid+1
        else:
            right=mid-1
    if flag:
        return 'found'
    else:
        return -1
```


### **3. Compare Searching**
Explain the difference between linear search and binary search. When would you use each? Give time complexity for both.

### **4. Search Implementation**
Write a function that searches for all occurrences of number 5 in `[5, 2, 5, 8, 5, 1]` and returns their indices.
## Answer
```python
pos=[]
arr=[5, 2, 5, 8, 5, 1]
for i in range(len(arr)):
    if arr[i]==5:
        pos.append(i)
print(pos)
```

---

## **SORTING (Questions 5-8)**

### **5. Bubble Sort**
Sort the array `[64, 34, 25, 12, 22, 11, 90]` using bubble sort. Show each pass clearly.
## Answer
```python
#Sort the array [64, 34, 25, 12, 22, 11, 90] using bubble sort. Show each pass clearly.

arr=[64, 34, 25, 12, 22, 11, 90]
n=len(arr)
for i in range(n):
    flag=False
    for j in range(n-1-i):
        if arr[j]>arr[j+1]:
            arr[j],arr[j+1]=arr[j+1],arr[j]
            flag=True
    if not flag:
        break
print(arr)
```

### **6. Insertion Sort**
Sort the array `[5, 2, 4, 6, 1, 3]` using insertion sort. Show how each element is inserted.
## Answer 
```python
#Sort the array [5, 2, 4, 6, 1, 3] using insertion sort. Show how each element is inserted.

arr=[5, 2, 4, 6, 1, 3]
for i in range(1,len(arr)):
    key=arr[i]
    j=i-1
    while j>=0 and arr[j]>key:
        arr[j+1]=arr[j]
        j-=1
    arr[j+1]=key

print(arr)
```

### **7. Sorting Comparison**
Compare bubble sort and insertion sort:
- Which is more efficient for nearly sorted data?
- What is the time complexity of each?
- Which is stable?

### **8. Trace Sorting**
Trace the insertion sort algorithm step-by-step for `[9, 5, 7, 3]`. Show the array after each insertion.

---

## **FUNCTIONS (Questions 9-12)**

### **9. Basic Function**
Write a function that takes a list of numbers and returns the sum of all even numbers.
Example: `[1, 2, 3, 4, 5, 6]` → Output: `12`

### **10. Recursive Function - Factorial**
Write a recursive function to calculate factorial of n.
Example: `factorial(5)` → `120`

### **11. Recursive Function - Sum**
Write a recursive function to find the sum of numbers from 1 to n.
Example: `sum_n(5)` → `15` (1+2+3+4+5)

### **12. Fibonacci Recursion**
Write a recursive function to find the nth Fibonacci number.
Example: `fibonacci(6)` → `8` (sequence: 0,1,1,2,3,5,8)

---

## **STACK (Questions 13-15)**

### **13. Stack Operations**
Perform the following operations on an empty stack and show the stack after each operation:
- Push 10
- Push 20
- Push 30
- Pop
- Push 40
- Peek
- Pop

  ## Answer
  ```python
  stack=[]
    top=-1
    def push(n):
        global top, stack
        stack.append(n)
        top+=1
        print(stack)
    def pop():
        global top, stack
        if top == -1:
            print('stack empty')
        else:
            pop_item=stack[top]
            top-=1
            stack= stack[:top+1]
            print(stack)
            
    def peek():
        global top, stack
        if top == -1:
            print('stack empty')
        else:
            print(stack[top])
    
    push(10)
    push(20)
    push(30)
    pop()
    push(40)
    peek()
    pop()
```

### **14. Reverse String Using Stack**
Write a function using stack to reverse the string "HELLO". Show how the stack changes at each step.

### **15. Balanced Parentheses**
Write a function using stack to check if parentheses are balanced:
- Input: `"({[]})"` → Output: `True`
- Input: `"({[})"` → Output: `False`

---

## **QUEUE (Questions 16-18)**

### **16. Linear Queue Operations**
Perform the following operations on an empty linear queue and show front, rear indices:
- Enqueue 5
- Enqueue 10
- Enqueue 15
- Dequeue
- Enqueue 20
- Dequeue
- Display queue

### **17. Circular Queue**
Given a circular queue of size 5, perform these operations and show the queue state:
- Enqueue 10, 20, 30, 40
- Dequeue twice
- Enqueue 50, 60, 70
Show how rear wraps around.

### **18. Queue vs Stack**
Explain the difference between Stack and Queue with real-life examples. What are LIFO and FIFO?

---

## **PYTHON BASICS & ARRAYS (Questions 19-20)**

### **19. Array/List Operations**
Given list `nums = [10, 20, 30, 40, 50]`:
- Add 60 at the end
- Insert 25 at index 2
- Remove element 30
- Find length of list
- Access 3rd element
- Slice first 3 elements

### **20. Mixed Problem**
Write a program that:
1. Takes a list of numbers as input: `[45, 12, 67, 23, 89, 34]`
2. Sorts it using insertion sort
3. Uses binary search to find if 23 exists
4. Uses a stack to reverse the sorted list
5. Displays all results

---

## **BONUS CONCEPTUAL QUESTIONS**

### **21. Time Complexity**
What is the time complexity of:
- Linear search?
- Binary search?
- Bubble sort?
- Insertion sort?

### **22. When to Use What?**
- When would you use linear search over binary search?
- When is insertion sort better than bubble sort?
- When would you use a stack vs a queue?

---

## **ANSWER FORMAT FOR EXAM:**

### **For Searching/Sorting:**
- Show initial array
- Show each step/pass
- Show final result
- Mention time complexity

### **For Functions:**
- Write complete function with parameters
- Add comments explaining logic
- Show example test case

### **For Stack/Queue:**
- Show structure at each step
- Mention front/rear/top positions
- Handle empty/full conditions

### **For Recursion:**
- Show base case
- Show recursive case
- Trace with an example

---



Good luck! 🎯📝
