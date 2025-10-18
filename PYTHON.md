# Python Pre-Mock Syllabus Notes

## Part 1: Python Basics

### Variables and Data Types
Variables store data. Python has these basic types:
- **int**: whole numbers (5, -10, 0)
- **float**: decimal numbers (3.14, -2.5)
- **str**: text ("hello", 'world')
- **bool**: True or False

```python
name = "Alice"  # string
age = 25        # integer
height = 5.6    # float
is_student = True  # boolean
```

### Operators
- **Arithmetic**: +, -, *, /, //, %, **
- **Comparison**: ==, !=, <, >, <=, >=
- **Logical**: and, or, not

```python
x = 10
y = 3
print(x + y)    # 13
print(x > y)    # True
print(x > 5 and y < 5)  # True
```

### Conditional Statements (if, elif, else)
```python
age = 15
if age >= 18:
    print("Adult")
elif age >= 13:
    print("Teenager")
else:
    print("Child")
```

### Loops

**while loop** - continues while condition is True:
```python
i = 0
while i < 5:
    print(i)
    i = i + 1
# Output: 0 1 2 3 4
```

**for loop** - repeats for each item:
```python
for i in range(5):
    print(i)
# Output: 0 1 2 3 4

for fruit in ["apple", "banana", "orange"]:
    print(fruit)
```

### Strings
```python
text = "Hello"
print(text[0])      # 'H' (index 0)
print(text[1:4])    # 'ell' (slicing)
print(len(text))    # 5
```

### Lists (Arrays)
A list stores multiple items in order. You can change items after creating it.

```python
fruits = ["apple", "banana", "orange"]
print(fruits[0])        # 'apple'
print(fruits[-1])       # 'orange' (last item)
print(len(fruits))      # 3

# Change item
fruits[0] = "pear"

# Loop through list
for fruit in fruits:
    print(fruit)
```

---

## Part 2: Searching Algorithms

### Linear Search
**What it does:** Check every item in the list one by one until you find what you're looking for.

**Why learn it:** Simple to understand. Works on unsorted lists.

**Explanation:** Imagine looking for your friend in a crowd. You check the first person, then the second, then the third... until you find them.

```python
def linear_search(list_items, target):
    """
    Search for target in list by checking each item
    Returns the index if found, -1 if not found
    """
    i = 0
    while i < len(list_items):
        if list_items[i] == target:
            return i  # Found it!
        i = i + 1
    return -1  # Not found

numbers = [5, 2, 8, 1, 9]
print(linear_search(numbers, 8))   # Output: 2
print(linear_search(numbers, 10))  # Output: -1
```

**How it works step by step:**
1. Start at index 0 (first item)
2. Compare it with what we're looking for
3. If it matches, return the index
4. If not, move to the next item (i = i + 1)
5. Repeat until found or reached end of list

**Time complexity:** Slow - might need to check every item (O(n))

---

### Binary Search
**What it does:** Jump to the middle of a SORTED list, check if target is there. If target is bigger, jump to middle of right side. If smaller, jump to middle of left side. Keep narrowing down.

**Why learn it:** Much faster! Only works on sorted lists.

**Explanation:** Like finding a word in a dictionary. You open to the middle. If the word comes after, skip the left half. If it comes before, skip the right half. Keep narrowing down.

```python
def binary_search(list_items, target):
    """
    Search for target in SORTED list using binary search
    Returns index if found, -1 if not found
    """
    left = 0
    right = len(list_items) - 1
    
    while left <= right:
        mid = (left + right) // 2  # Find middle index
        
        if list_items[mid] == target:
            return mid  # Found it!
        elif list_items[mid] < target:
            # Target is bigger, search right side
            left = mid + 1
        else:
            # Target is smaller, search left side
            right = mid - 1
    
    return -1  # Not found

numbers = [1, 2, 5, 8, 9]  # Must be SORTED
print(binary_search(numbers, 8))   # Output: 3
print(binary_search(numbers, 10))  # Output: -1
```

**How it works step by step:**
1. List must be sorted: [1, 2, 5, 8, 9]
2. Find middle: index 2 (value 5)
3. Looking for 8: 8 > 5, so ignore left side
4. New left=3, right=4, middle is 8
5. Found! Return index 3

**Time complexity:** Fast - eliminates half with each step (O(log n))

**Difference:** Binary search is faster but list must be sorted. Linear search works on any list but is slower.

---

## Part 3: Sorting Algorithms

### Bubble Sort
**What it does:** Compare pairs of items side by side. If the left one is bigger, swap them. Keep doing this until the list is sorted.

**Why learn it:** Easy to understand. Shows basic sorting concept.

**Explanation:** Imagine bubbles floating up - bigger values "bubble" to the right like they're floating to the top.

```python
def bubble_sort(list_items):
    """
    Sort list using bubble sort
    Modifies the original list
    """
    n = len(list_items)
    
    # Outer loop: repeat n times
    i = 0
    while i < n:
        # Inner loop: compare pairs
        j = 0
        while j < n - i - 1:
            # If left item is bigger than right item, swap
            if list_items[j] > list_items[j + 1]:
                # Manual swap (don't use Python's built-in swap)
                temp = list_items[j]
                list_items[j] = list_items[j + 1]
                list_items[j + 1] = temp
            j = j + 1
        i = i + 1
    
    return list_items

numbers = [5, 2, 8, 1, 9]
print(bubble_sort(numbers))  # Output: [1, 2, 5, 8, 9]
```

**How it works step by step with [5, 2, 8, 1, 9]:**

**Pass 1:** Compare adjacent pairs, swap if needed
- Compare 5 & 2 → swap → [2, 5, 8, 1, 9]
- Compare 5 & 8 → no swap → [2, 5, 8, 1, 9]
- Compare 8 & 1 → swap → [2, 5, 1, 8, 9]
- Compare 8 & 9 → no swap → [2, 5, 1, 8, 9]

**Pass 2:** Largest is now at end, repeat with smaller list
- Compare 2 & 5 → no swap → [2, 5, 1, 8, 9]
- Compare 5 & 1 → swap → [2, 1, 5, 8, 9]
- Compare 5 & 8 → no swap → [2, 1, 5, 8, 9]

And so on until sorted...

**Final:** [1, 2, 5, 8, 9]

**Time complexity:** Slow - compares many pairs (O(n²))

---

### Insertion Sort
**What it does:** Build a sorted list one item at a time. Take each unsorted item and insert it into the correct position in the sorted part.

**Why learn it:** More efficient than bubble sort. Intuitive method.

**Explanation:** Like sorting playing cards in your hand. You pick up cards one by one and place them in the right position among the cards you already sorted.

```python
def insertion_sort(list_items):
    """
    Sort list using insertion sort
    """
    n = len(list_items)
    
    # Start from second item (index 1)
    i = 1
    while i < n:
        key = list_items[i]  # Current item to insert
        j = i - 1
        
        # Shift items right until we find correct position
        while j >= 0 and list_items[j] > key:
            list_items[j + 1] = list_items[j]
            j = j - 1
        
        # Insert at correct position
        list_items[j + 1] = key
        i = i + 1
    
    return list_items

numbers = [5, 2, 8, 1, 9]
print(insertion_sort(numbers))  # Output: [1, 2, 5, 8, 9]
```

**How it works step by step with [5, 2, 8, 1, 9]:**

**Step 1:** List starts [5] (sorted), pick 2
- 2 < 5, shift 5 right → [5, 5], insert 2 → [2, 5]

**Step 2:** List is [2, 5] (sorted), pick 8
- 8 > 5, insert at end → [2, 5, 8]

**Step 3:** List is [2, 5, 8] (sorted), pick 1
- 1 < 2, shift everything right → [2, 5, 8], insert 1 → [1, 2, 5, 8]

**Step 4:** List is [1, 2, 5, 8] (sorted), pick 9
- 9 > 8, insert at end → [1, 2, 5, 8, 9]

**Final:** [1, 2, 5, 8, 9]

**Time complexity:** Medium - faster than bubble sort in many cases (O(n²) worst, but better average)

---

## Part 4: Functions

### Basic Functions
A function is reusable code. Define it once, use it many times.

```python
def greet(name):
    """This function greets someone"""
    print("Hello, " + name)

greet("Alice")  # Output: Hello, Alice
greet("Bob")    # Output: Hello, Bob
```

**Functions with return:**
```python
def add(a, b):
    result = a + b
    return result

total = add(5, 3)
print(total)  # Output: 8
```

**Function with default values:**
```python
def introduce(name, age=18):
    message = "My name is " + name + " and I'm " + str(age) + " years old"
    print(message)

introduce("Alice")           # Uses default age
introduce("Bob", 25)         # Uses provided age
```

---

### Recursive Functions
**What it does:** A function that calls itself.

**Why learn it:** Some problems are easier to solve with recursion.

**Explanation:** Like looking in a mirror that reflects another mirror - each reflection calls the previous one.

**Important:** Recursion needs a **base case** (when to stop) or it runs forever.

```python
def countdown(n):
    """Count down from n to 1"""
    # BASE CASE: When to stop
    if n == 0:
        print("Blastoff!")
        return
    
    # RECURSIVE CASE: Call itself
    print(n)
    countdown(n - 1)

countdown(3)
# Output:
# 3
# 2
# 1
# Blastoff!
```

**How it works:** countdown(3)
- Print 3, call countdown(2)
- Print 2, call countdown(1)
- Print 1, call countdown(0)
- Base case: stop and print "Blastoff!"

**Recursive Factorial:**
```python
def factorial(n):
    """
    Factorial: n! = n × (n-1) × (n-2) × ... × 1
    Example: 5! = 5 × 4 × 3 × 2 × 1 = 120
    """
    # BASE CASE
    if n == 0 or n == 1:
        return 1
    
    # RECURSIVE CASE
    return n * factorial(n - 1)

print(factorial(5))  # Output: 120
```

**How it works:** factorial(5)
- Can't solve yet, call factorial(4)
- Can't solve yet, call factorial(3)
- Can't solve yet, call factorial(2)
- Can't solve yet, call factorial(1)
- Base case! Return 1
- Now work backwards: 2×1=2, 3×2=6, 4×6=24, 5×24=120

---

## Part 5: Stack

**What is a Stack?** Think of stacking plates. Last plate you put on top is the first one you take off.

**Key concept:** LIFO - Last In First Out

### Linear Stack (Built from scratch)
```python
class Stack:
    def __init__(self):
        self.items = []
    
    def add_to_top(self, item):
        """Add item to top of stack"""
        self.items[len(self.items):] = [item]
    
    def remove_from_top(self):
        """Remove and return item from top"""
        if self.is_empty():
            return None
        last_item = self.items[len(self.items) - 1]
        self.items = self.items[0:len(self.items) - 1]
        return last_item
    
    def see_top(self):
        """See top item without removing"""
        if self.is_empty():
            return None
        return self.items[len(self.items) - 1]
    
    def is_empty(self):
        """Check if stack is empty"""
        return len(self.items) == 0
    
    def get_size(self):
        """Return number of items"""
        return len(self.items)

# Using the stack
stack = Stack()
stack.add_to_top(1)
stack.add_to_top(2)
stack.add_to_top(3)
print(stack.see_top())       # Output: 3 (top item)
print(stack.remove_from_top())  # Output: 3 (remove and return)
print(stack.remove_from_top())  # Output: 2
print(stack.get_size())      # Output: 1
```

**Manual implementation of add and remove:**
```python
# Instead of using built-in list.append():
# We manually add to the end using slicing:
self.items = self.items + [item]

# Instead of using built-in list.pop():
# We manually remove from end using slicing:
self.items = self.items[0:len(self.items) - 1]
```

**Real-world example:** Browser back button
- Click link 1 → stack: [1]
- Click link 2 → stack: [1, 2]
- Click link 3 → stack: [1, 2, 3]
- Click back → remove_from_top() → go to link 2
- Click back → remove_from_top() → go to link 1

---

### Circular Stack
A circular stack uses a fixed size and wraps around. When you reach the end, you go back to the beginning.

```python
class CircularStack:
    def __init__(self, size):
        self.size = size
        self.items = []
        i = 0
        while i < size:
            self.items = self.items + [None]
            i = i + 1
        self.top = -1  # No items yet
    
    def add_to_stack(self, item):
        """Add item"""
        if self.is_full():
            print("Stack is full!")
            return
        # Move top pointer: wraps around using modulo
        self.top = (self.top + 1) % self.size
        # Replace item at that position
        self.items[self.top] = item
    
    def remove_from_stack(self):
        """Remove item"""
        if self.is_empty():
            return None
        item = self.items[self.top]
        self.items[self.top] = None
        # Move top pointer back: wraps around using modulo
        self.top = (self.top - 1) % self.size
        return item
    
    def is_empty(self):
        return self.top == -1
    
    def is_full(self):
        return self.top == self.size - 1

stack = CircularStack(3)
stack.add_to_stack(1)  # position 0
stack.add_to_stack(2)  # position 1
stack.add_to_stack(3)  # position 2
print(stack.remove_from_stack())  # Output: 3
print(stack.remove_from_stack())  # Output: 2
```

---

## Part 6: Queue

**What is a Queue?** Think of people waiting in line. First person in line is first to leave.

**Key concept:** FIFO - First In First Out

### Linear Queue (Built from scratch)
```python
class Queue:
    def __init__(self):
        self.items = []
    
    def add_to_back(self, item):
        """Add item to back of queue"""
        self.items = self.items + [item]
    
    def remove_from_front(self):
        """Remove and return item from front"""
        if self.is_empty():
            return None
        first_item = self.items[0]
        self.items = self.items[1:len(self.items)]
        return first_item
    
    def see_front(self):
        """See front item without removing"""
        if self.is_empty():
            return None
        return self.items[0]
    
    def is_empty(self):
        """Check if queue is empty"""
        return len(self.items) == 0
    
    def get_size(self):
        """Return number of items"""
        return len(self.items)

# Using the queue
queue = Queue()
queue.add_to_back('A')
queue.add_to_back('B')
queue.add_to_back('C')
print(queue.see_front())        # Output: A (front item)
print(queue.remove_from_front()) # Output: A (first to leave)
print(queue.remove_from_front()) # Output: B
print(queue.get_size())         # Output: 1
```

**Manual implementation:**
```python
# Instead of append(), add to back using list concatenation:
self.items = self.items + [item]

# Instead of pop(0), remove from front using slicing:
self.items = self.items[1:len(self.items)]
```

**Real-world example:** Customer service queue
- Customer A arrives → queue: [A]
- Customer B arrives → queue: [A, B]
- Customer C arrives → queue: [A, B, C]
- Service A → remove_from_front() → queue: [B, C]
- Service B → remove_from_front() → queue: [C]

---

### Circular Queue
A circular queue uses a fixed size. Front and rear pointers move around the circle.

```python
class CircularQueue:
    def __init__(self, size):
        self.size = size
        self.items = []
        i = 0
        while i < size:
            self.items = self.items + [None]
            i = i + 1
        self.front = -1
        self.rear = -1
    
    def add_to_queue(self, item):
        """Add item to queue"""
        # Check if queue is full
        next_rear = (self.rear + 1) % self.size
        if next_rear == self.front and self.front != -1:
            print("Queue is full!")
            return
        
        # If first item, set front to 0
        if self.front == -1:
            self.front = 0
        
        # Move rear pointer and add item
        self.rear = next_rear
        self.items[self.rear] = item
    
    def remove_from_queue(self):
        """Remove item from queue"""
        if self.front == -1:
            print("Queue is empty!")
            return None
        
        item = self.items[self.front]
        
        # If this was last item, reset
        if self.front == self.rear:
            self.front = -1
            self.rear = -1
        else:
            # Move front pointer forward (wraps around)
            self.front = (self.front + 1) % self.size
        
        return item
    
    def is_empty(self):
        return self.front == -1

queue = CircularQueue(3)
queue.add_to_queue('A')  # rear: 0
queue.add_to_queue('B')  # rear: 1
queue.add_to_queue('C')  # rear: 2
print(queue.remove_from_queue())  # Output: A, front: 1
print(queue.remove_from_queue())  # Output: B, front: 2
queue.add_to_queue('D')           # rear wraps to 0
```

---

## Quick Comparison

| Algorithm | Best For | Speed | Sorted? |
|-----------|----------|-------|---------|
| Linear Search | Small lists, any data | Slow | No |
| Binary Search | Large lists | Fast | Yes |
| Bubble Sort | Teaching | Slow | Yes |
| Insertion Sort | Small/medium lists | Medium | Yes |
| Stack | LIFO needs (undo, brackets) | Fast | N/A |
| Queue | FIFO needs (waiting) | Fast | N/A |

---

## Tips for Exam

1. **Understand, don't memorize** - Know WHY each algorithm works
2. **Trace through examples** - Draw out how [5,2,8,1,9] gets sorted
3. **Know the differences** - Linear vs Binary, Stack vs Queue, LIFO vs FIFO
4. **Base cases matter** - Recursion needs a stop condition
5. **Practice code** - Type out the code yourself, don't just read
6. **No built-in functions** - Implement logic from scratch using basic operations
