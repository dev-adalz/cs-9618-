# Cambridge A Level Computer Science 9618 - Complete Theory Notes

## 9. Algorithm Design and Problem-solving

### 9.1 Computational Thinking Skills

#### **Abstraction**

**What is Abstraction?**
Abstraction is the process of removing unnecessary details and focusing only on the essential features relevant to solving a problem. It simplifies complex systems by hiding complexity.

**Purpose of Abstraction:**
- Makes problems more manageable by reducing complexity
- Allows focus on the most important aspects of a problem
- Enables creation of general solutions that can be reused
- Facilitates communication between stakeholders by using simplified models

**Need for and Benefits of Abstraction:**
1. **Simplification** - Complex real-world systems become easier to understand
2. **Efficiency** - Saves time by not considering irrelevant details
3. **Reusability** - Abstract models can be applied to multiple similar problems
4. **Communication** - Easier to explain and document solutions
5. **Focus** - Developers can concentrate on core functionality

**Producing an Abstract Model:**
To create an abstract model, only include essential details:
- Identify the key components of the system
- Remove unnecessary implementation details
- Focus on relationships and behaviors that matter
- Represent the system at an appropriate level of detail

**Example:**
When modeling a student registration system:
- **Include:** Student ID, Name, Course, Enrollment Date
- **Exclude:** Hair color, favorite food, shoe size (not relevant to registration)

#### **Decomposition**

**What is Decomposition?**
Decomposition is breaking down a complex problem into smaller, more manageable sub-problems that can be solved independently.

**Purpose of Decomposition:**
- Makes complex problems easier to solve
- Allows multiple people to work on different parts simultaneously
- Leads to the concept of program modules (procedures/functions)
- Facilitates testing and debugging of individual components
- Enables code reuse

**How to Decompose Problems:**
1. Identify the main task
2. Break it into logical subtasks
3. Further break down subtasks if they're still complex
4. Continue until each subtask is simple enough to solve directly
5. Each subtask becomes a potential procedure or function

**Example: Library Management System**
- Main Problem: Library Management
  - Sub-problem 1: Book Management
    - Add new book
    - Remove book
    - Search for book
  - Sub-problem 2: Member Management
    - Register member
    - Remove member
    - Update member details
  - Sub-problem 3: Loan Management
    - Issue book
    - Return book
    - Calculate fines

---

### 9.2 Algorithms

#### **Understanding Algorithms**

**Definition:**
An algorithm is a solution to a problem expressed as a sequence of defined steps. It is a precise, unambiguous set of instructions that can be followed to solve a problem or complete a task.

**Characteristics of Good Algorithms:**
- **Finite** - Must terminate after a finite number of steps
- **Definite** - Each step must be precisely defined
- **Input** - Should have zero or more inputs
- **Output** - Should produce at least one output
- **Effective** - Steps must be basic enough to be carried out

#### **Identifier Names and Tables**

**Suitable Identifier Names:**
- Should be descriptive and meaningful
- Use camelCase or snake_case consistently
- Avoid single letters except for loop counters (i, j, k)
- Should indicate the data's purpose

**Identifier Table Example:**
```
Identifier      | Data Type | Description
----------------|-----------|---------------------------
studentName     | STRING    | Name of the student
studentAge      | INTEGER   | Age of the student
isEnrolled      | BOOLEAN   | Enrollment status
averageScore    | REAL      | Average test score
currentDate     | DATE      | Today's date
```

#### **Basic Algorithm Constructs**

**1. Sequence**
Instructions executed one after another in order.

```pseudocode
// Example: Calculate area of rectangle
INPUT length
INPUT width
area ← length * width
OUTPUT area
```

**2. Selection (Decision Making)**
Choosing different paths based on conditions.

**IF Statement:**
```pseudocode
IF condition THEN
    // statements
ENDIF

// With ELSE clause
IF age >= 18 THEN
    OUTPUT "Adult"
ELSE
    OUTPUT "Minor"
ENDIF

// Nested IF
IF score >= 70 THEN
    IF score >= 90 THEN
        grade ← "A"
    ELSE
        grade ← "B"
    ENDIF
ELSE
    grade ← "C"
ENDIF
```

**CASE Statement:**
```pseudocode
CASE OF choice
    1: OUTPUT "Option 1 selected"
    2: OUTPUT "Option 2 selected"
    3: OUTPUT "Option 3 selected"
    OTHERWISE OUTPUT "Invalid option"
ENDCASE
```

**3. Iteration (Repetition/Loops)**

**Count-Controlled Loop (FOR loop):**
Used when you know how many times to repeat.

```pseudocode
FOR counter ← 1 TO 10
    OUTPUT counter
NEXT counter

// With step
FOR i ← 0 TO 100 STEP 5
    OUTPUT i
NEXT i
```

**Pre-condition Loop (WHILE loop):**
Condition checked before execution. May not execute at all.

```pseudocode
WHILE condition DO
    // statements
ENDWHILE

// Example
counter ← 1
WHILE counter <= 10 DO
    OUTPUT counter
    counter ← counter + 1
ENDWHILE
```

**Post-condition Loop (REPEAT-UNTIL loop):**
Condition checked after execution. Always executes at least once.

```pseudocode
REPEAT
    // statements
UNTIL condition

// Example
counter ← 1
REPEAT
    OUTPUT counter
    counter ← counter + 1
UNTIL counter > 10
```

**Choosing Loop Structures:**
- **FOR loop**: Use when number of iterations is known
- **WHILE loop**: Use when condition needs checking before execution
- **REPEAT-UNTIL**: Use when loop must execute at least once

#### **Documenting Algorithms**

**1. Structured English**
Plain English with programming-like structure:
```
Read student name
Read student marks
If marks is greater than or equal to 50 then
    Display "Pass"
Otherwise
    Display "Fail"
End if
```

**2. Flowchart Symbols**
- **Oval/Terminal**: Start/End
- **Parallelogram**: Input/Output
- **Rectangle**: Process/Calculation
- **Diamond**: Decision
- **Arrow**: Flow direction

**3. Pseudocode**
See examples above (formal notation between code and English)

#### **Stepwise Refinement**

**What is Stepwise Refinement?**
The process of breaking down an algorithm into progressively more detailed levels until each step is simple enough to be programmed directly.

**Process:**
1. Start with a high-level description of the problem
2. Break down each step into more detailed sub-steps
3. Continue refining until each step is a simple operation
4. Each refinement adds more detail without changing the overall logic

**Example: Calculate Student Average**

**Level 1 (High-level):**
```
1. Get student marks
2. Calculate average
3. Display result
```

**Level 2 (More detail):**
```
1. Get student marks
   1.1 Initialize total to 0
   1.2 For each subject
       1.2.1 Input mark
       1.2.2 Add mark to total
2. Calculate average
   2.1 Divide total by number of subjects
3. Display result
   3.1 Output average
```

**Level 3 (Programming detail):**
```pseudocode
total ← 0
numSubjects ← 5

FOR i ← 1 TO numSubjects
    OUTPUT "Enter mark for subject ", i
    INPUT mark
    total ← total + mark
NEXT i

average ← total / numSubjects
OUTPUT "Average: ", average
```

#### **Logic Statements**

Logic statements use Boolean operators to define conditions:

**Logical Operators:**
- **AND**: Both conditions must be true
- **OR**: At least one condition must be true
- **NOT**: Reverses the truth value

```pseudocode
// AND example
IF age >= 18 AND hasLicense = TRUE THEN
    OUTPUT "Can drive"
ENDIF

// OR example
IF day = "Saturday" OR day = "Sunday" THEN
    OUTPUT "Weekend"
ENDIF

// NOT example
IF NOT isRaining THEN
    OUTPUT "Go outside"
ENDIF

// Complex logic
IF (score >= 50 AND attendance >= 75) OR hasExemption = TRUE THEN
    OUTPUT "Eligible for exam"
ENDIF
```

---

## 10. Data Types and Structures

### 10.1 Data Types and Records

#### **Basic Data Types**

**1. INTEGER**
- Whole numbers (positive, negative, or zero)
- No decimal places
- Example: -5, 0, 42, 1000

```pseudocode
DECLARE age : INTEGER
DECLARE quantity : INTEGER
age ← 25
quantity ← 100
```

**2. REAL**
- Numbers with decimal places
- Floating-point numbers
- Example: 3.14, -0.5, 100.0

```pseudocode
DECLARE price : REAL
DECLARE temperature : REAL
price ← 19.99
temperature ← -5.6
```

**3. CHAR**
- Single character
- Letters, digits, or symbols
- Example: 'A', '5', '$'

```pseudocode
DECLARE grade : CHAR
DECLARE initial : CHAR
grade ← 'A'
initial ← 'J'
```

**4. STRING**
- Sequence of characters
- Text data
- Example: "Hello", "Computer Science"

```pseudocode
DECLARE name : STRING
DECLARE address : STRING
name ← "John Smith"
address ← "123 Main Street"
```

**5. BOOLEAN**
- Logical values only
- TRUE or FALSE
- Used for conditions and flags

```pseudocode
DECLARE isValid : BOOLEAN
DECLARE hasAccess : BOOLEAN
isValid ← TRUE
hasAccess ← FALSE
```

**6. DATE**
- Calendar dates
- Format may vary (DD/MM/YYYY, etc.)

```pseudocode
DECLARE birthDate : DATE
DECLARE enrollmentDate : DATE
birthDate ← 15/03/2005
```

#### **Selecting Appropriate Data Types**

| Data to Store | Appropriate Type | Reason |
|---------------|------------------|--------|
| Age | INTEGER | Whole number, no decimals needed |
| Price | REAL | May include cents/pence |
| Name | STRING | Multiple characters |
| Gender (M/F) | CHAR | Single character sufficient |
| Is Passed | BOOLEAN | Yes/No (TRUE/FALSE) |
| Birth Date | DATE | Calendar date |

#### **Record Structures**

**What is a Record?**
A record (also called a structure or composite data type) is a collection of related data items of different types stored under one identifier.

**Purpose of Records:**
- Group related data together logically
- Store different data types for one entity
- Make data management easier
- Represent real-world entities (students, products, employees)

**Defining a Record Structure:**

```pseudocode
// Define record type
TYPE Student
    DECLARE studentID : STRING
    DECLARE name : STRING
    DECLARE age : INTEGER
    DECLARE gradeAverage : REAL
    DECLARE isEnrolled : BOOLEAN
ENDTYPE

// Declare a variable of that type
DECLARE pupil1 : Student
DECLARE pupil2 : Student
```

**Writing Data to a Record:**

```pseudocode
// Assigning values to record fields
pupil1.studentID ← "S12345"
pupil1.name ← "Alice Johnson"
pupil1.age ← 17
pupil1.gradeAverage ← 85.5
pupil1.isEnrolled ← TRUE
```

**Reading Data from a Record:**

```pseudocode
// Accessing record fields
OUTPUT "Student ID: ", pupil1.studentID
OUTPUT "Name: ", pupil1.name
OUTPUT "Age: ", pupil1.age
OUTPUT "Average: ", pupil1.gradeAverage

IF pupil1.isEnrolled = TRUE THEN
    OUTPUT "Currently enrolled"
ENDIF
```

**Complete Example:**

```pseudocode
// Define record type for book
TYPE Book
    DECLARE isbn : STRING
    DECLARE title : STRING
    DECLARE author : STRING
    DECLARE price : REAL
    DECLARE inStock : BOOLEAN
ENDTYPE

// Declare variable
DECLARE myBook : Book

// Input data
INPUT myBook.isbn
INPUT myBook.title
INPUT myBook.author
INPUT myBook.price
INPUT myBook.inStock

// Output data
OUTPUT "Book Details:"
OUTPUT "ISBN: ", myBook.isbn
OUTPUT "Title: ", myBook.title
OUTPUT "Author: ", myBook.author
OUTPUT "Price: $", myBook.price
IF myBook.inStock THEN
    OUTPUT "Available"
ELSE
    OUTPUT "Out of stock"
ENDIF
```

---

### 10.2 Arrays

#### **Array Fundamentals**

**What is an Array?**
An array is a data structure that stores multiple values of the same data type under a single identifier, accessed using an index.

**Key Terminology:**
- **Index**: The position of an element in the array (usually starts at 0)
- **Element**: An individual value stored in the array
- **Lower Bound**: The smallest index value (usually 0)
- **Upper Bound**: The largest index value (size - 1)
- **Subscript**: Another term for index

#### **One-Dimensional (1D) Arrays**

**Declaration:**

```pseudocode
// Declare array
DECLARE scores : ARRAY[0:9] OF INTEGER
// Creates array with 10 elements (indices 0 to 9)

DECLARE names : ARRAY[0:4] OF STRING
// Creates array with 5 elements (indices 0 to 4)

DECLARE temperatures : ARRAY[1:7] OF REAL
// Creates array with 7 elements (indices 1 to 7)
```

**Assigning Values:**

```pseudocode
// Assign individual elements
scores[0] ← 85
scores[1] ← 92
scores[2] ← 78

// Using a loop to assign values
FOR i ← 0 TO 9
    INPUT scores[i]
NEXT i
```

**Accessing Values:**

```pseudocode
// Access individual element
OUTPUT scores[0]

// Access all elements
FOR i ← 0 TO 9
    OUTPUT "Score ", i, ": ", scores[i]
NEXT i
```

**Common 1D Array Operations:**

```pseudocode
// Find sum of all elements
total ← 0
FOR i ← 0 TO 9
    total ← total + scores[i]
NEXT i

// Find maximum value
max ← scores[0]
FOR i ← 1 TO 9
    IF scores[i] > max THEN
        max ← scores[i]
    ENDIF
NEXT i

// Find minimum value
min ← scores[0]
FOR i ← 1 TO 9
    IF scores[i] < min THEN
        min ← scores[i]
    ENDIF
NEXT i

// Calculate average
total ← 0
FOR i ← 0 TO 9
    total ← total + scores[i]
NEXT i
average ← total / 10
```

#### **Two-Dimensional (2D) Arrays**

**Declaration:**

```pseudocode
// Declare 2D array
DECLARE grid : ARRAY[0:2, 0:3] OF INTEGER
// Creates 3x4 array (3 rows, 4 columns)

DECLARE classroom : ARRAY[0:4, 0:5] OF STRING
// Creates 5x6 array
```

**Visualizing 2D Arrays:**
```
grid[row, column]

     Col0  Col1  Col2  Col3
Row0 [  ] [  ] [  ] [  ]
Row1 [  ] [  ] [  ] [  ]
Row2 [  ] [  ] [  ] [  ]
```

**Assigning Values:**

```pseudocode
// Assign individual element
grid[0, 0] ← 10
grid[1, 2] ← 25

// Using nested loops
FOR row ← 0 TO 2
    FOR col ← 0 TO 3
        INPUT grid[row, col]
    NEXT col
NEXT row
```

**Accessing Values:**

```pseudocode
// Access individual element
OUTPUT grid[1, 2]

// Access all elements
FOR row ← 0 TO 2
    FOR col ← 0 TO 3
        OUTPUT grid[row, col], " "
    NEXT col
    OUTPUT ""  // New line after each row
NEXT row
```

**Common 2D Array Operations:**

```pseudocode
// Sum of all elements
total ← 0
FOR row ← 0 TO 2
    FOR col ← 0 TO 3
        total ← total + grid[row, col]
    NEXT col
NEXT row

// Sum of a specific row
rowSum ← 0
targetRow ← 1
FOR col ← 0 TO 3
    rowSum ← rowSum + grid[targetRow, col]
NEXT col

// Sum of a specific column
colSum ← 0
targetCol ← 2
FOR row ← 0 TO 2
    colSum ← colSum + grid[row, targetCol]
NEXT row
```

#### **Selecting Appropriate Array Structure**

**Use 1D Array when:**
- Storing a simple list of values
- Data is linear (e.g., test scores for one class)
- Only one dimension needed (e.g., days of the week)

**Use 2D Array when:**
- Representing tabular data (rows and columns)
- Working with grids or matrices
- Data has two dimensions (e.g., seating chart, chess board)

**Examples:**
- Student scores for one class → 1D array
- Student scores for multiple classes → 2D array
- Daily temperatures for one week → 1D array
- Daily temperatures for multiple weeks → 2D array

#### **Searching: Linear Search**

**What is Linear Search?**
A search algorithm that checks each element in sequence until the target is found or the end is reached.

**Characteristics:**
- Simple to implement
- Works on unsorted data
- Time complexity: O(n)
- Checks elements one by one

**Pseudocode:**

```pseudocode
// Linear search in 1D array
DECLARE numbers : ARRAY[0:9] OF INTEGER
DECLARE target : INTEGER
DECLARE found : BOOLEAN
DECLARE position : INTEGER

found ← FALSE
position ← -1

INPUT target

FOR i ← 0 TO 9
    IF numbers[i] = target THEN
        found ← TRUE
        position ← i
        BREAK  // Exit loop early
    ENDIF
NEXT i

IF found THEN
    OUTPUT "Found at position ", position
ELSE
    OUTPUT "Not found"
ENDIF
```

**Alternative Version (with early exit):**

```pseudocode
FUNCTION LinearSearch(arr : ARRAY OF INTEGER, target : INTEGER) RETURNS INTEGER
    FOR i ← 0 TO LENGTH(arr) - 1
        IF arr[i] = target THEN
            RETURN i  // Return position if found
        ENDIF
    NEXT i
    RETURN -1  // Return -1 if not found
ENDFUNCTION
```

#### **Sorting: Bubble Sort**

**What is Bubble Sort?**
A sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they're in the wrong order.

**How it Works:**
1. Compare first two elements
2. Swap if in wrong order
3. Move to next pair
4. Repeat until list is sorted
5. Multiple passes may be needed

**Characteristics:**
- Simple to understand
- Works in-place (no extra memory needed)
- Time complexity: O(n²)
- Inefficient for large datasets

**Pseudocode (Basic Version):**

```pseudocode
DECLARE numbers : ARRAY[0:9] OF INTEGER
DECLARE temp : INTEGER

// Perform multiple passes
FOR i ← 0 TO 8
    FOR j ← 0 TO 8 - i
        IF numbers[j] > numbers[j + 1] THEN
            // Swap elements
            temp ← numbers[j]
            numbers[j] ← numbers[j + 1]
            numbers[j + 1] ← temp
        ENDIF
    NEXT j
NEXT i
```

**Optimized Version (with flag):**

```pseudocode
DECLARE numbers : ARRAY[0:9] OF INTEGER
DECLARE temp : INTEGER
DECLARE swapped : BOOLEAN
DECLARE n : INTEGER

n ← 10

REPEAT
    swapped ← FALSE
    FOR i ← 0 TO n - 2
        IF numbers[i] > numbers[i + 1] THEN
            // Swap
            temp ← numbers[i]
            numbers[i] ← numbers[i + 1]
            numbers[i + 1] ← temp
            swapped ← TRUE
        ENDIF
    NEXT i
    n ← n - 1
UNTIL NOT swapped
```

**Example Trace:**
```
Initial: [5, 2, 8, 1, 9]

Pass 1:
[2, 5, 8, 1, 9]  (5 and 2 swapped)
[2, 5, 8, 1, 9]  (5 and 8 not swapped)
[2, 5, 1, 8, 9]  (8 and 1 swapped)
[2, 5, 1, 8, 9]  (8 and 9 not swapped)

Pass 2:
[2, 5, 1, 8, 9]  (2 and 5 not swapped)
[2, 1, 5, 8, 9]  (5 and 1 swapped)
[2, 1, 5, 8, 9]  (5 and 8 not swapped)

Pass 3:
[1, 2, 5, 8, 9]  (2 and 1 swapped)

Sorted: [1, 2, 5, 8, 9]
```

---

### 10.3 Files

#### **Why Files are Needed**

**Purpose of Files:**
- **Persistent Storage**: Data survives after program terminates
- **Large Data Sets**: Handle more data than memory can hold
- **Data Sharing**: Share data between different programs
- **Backup**: Create copies of important data
- **Data Transfer**: Move data between systems

**Advantages:**
- Permanent storage (not lost when program ends)
- Can store large amounts of data
- Accessible by multiple programs
- Can be edited externally
- Easy to backup and archive

**Disadvantages:**
- Slower access than memory
- Requires file handling operations
- Risk of corruption
- Need to manage file paths and permissions

#### **Text Files**

**Characteristics:**
- Contain human-readable characters
- One or more lines of text
- Each line typically ends with newline character
- Can be opened in text editors

**File Operations:**

```pseudocode
// Opening a file for reading
OPENFILE "data.txt" FOR READ

// Opening a file for writing (creates new or overwrites)
OPENFILE "output.txt" FOR WRITE

// Opening a file for appending (adds to end)
OPENFILE "log.txt" FOR APPEND
```

**Reading from a File:**

```pseudocode
// Read single line
OPENFILE "data.txt" FOR READ
READFILE "data.txt", line
OUTPUT line
CLOSEFILE "data.txt"

// Read all lines
OPENFILE "data.txt" FOR READ
WHILE NOT EOF("data.txt")
    READFILE "data.txt", line
    OUTPUT line
ENDWHILE
CLOSEFILE "data.txt"
```

**Writing to a File:**

```pseudocode
// Write single line
OPENFILE "output.txt" FOR WRITE
WRITEFILE "output.txt", "Hello World"
CLOSEFILE "output.txt"

// Write multiple lines
OPENFILE "output.txt" FOR WRITE
FOR i ← 1 TO 5
    WRITEFILE "output.txt", "Line " & STR(i)
NEXT i
CLOSEFILE "output.txt"
```

**Complete File Processing Example:**

```pseudocode
// Read numbers from file, calculate average, write result

DECLARE total : REAL
DECLARE count : INTEGER
DECLARE number : REAL
DECLARE average : REAL

total ← 0
count ← 0

// Read numbers
OPENFILE "numbers.txt" FOR READ
WHILE NOT EOF("numbers.txt")
    READFILE "numbers.txt", number
    total ← total + number
    count ← count + 1
ENDWHILE
CLOSEFILE "numbers.txt"

// Calculate average
IF count > 0 THEN
    average ← total / count
    
    // Write result
    OPENFILE "result.txt" FOR WRITE
    WRITEFILE "result.txt", "Average: " & STR(average)
    CLOSEFILE "result.txt"
ENDIF
```

**Reading Records from File:**

```pseudocode
TYPE Student
    DECLARE id : STRING
    DECLARE name : STRING
    DECLARE score : INTEGER
ENDTYPE

DECLARE pupil : Student

OPENFILE "students.txt" FOR READ
WHILE NOT EOF("students.txt")
    READFILE "students.txt", pupil.id
    READFILE "students.txt", pupil.name
    READFILE "students.txt", pupil.score
    
    OUTPUT pupil.name, ": ", pupil.score
ENDWHILE
CLOSEFILE "students.txt"
```

---

### 10.4 Introduction to Abstract Data Types (ADT)

#### **What is an Abstract Data Type?**

**Definition:**
An ADT is a collection of data and a set of operations on those data. It defines what operations can be performed but not how they're implemented.

**Key Concepts:**
- **Data**: The information stored
- **Operations**: Actions that can be performed on the data
- **Encapsulation**: Implementation details are hidden
- **Interface**: Only the operations are exposed

**Why Use ADTs?**
- Simplifies programming (use without knowing implementation)
- Improves code organization
- Allows changing implementation without affecting code that uses it
- Provides reusable components

---

#### **STACK**

**What is a Stack?**
A Last-In-First-Out (LIFO) data structure. The last item added is the first to be removed (like a stack of plates).

**Key Features:**
- LIFO ordering
- Access only at one end (top)
- Two main operations: push and pop

**Operations:**
1. **Push**: Add item to top of stack
2. **Pop**: Remove item from top of stack
3. **Peek/Top**: View top item without removing
4. **IsEmpty**: Check if stack is empty
5. **IsFull**: Check if stack is full

**When to Use Stacks:**
- Function call management (call stack)
- Undo functionality in applications
- Expression evaluation
- Backtracking algorithms
- Browser history (back button)
- Reversing data

**Stack Using Array Implementation:**

```pseudocode
// Stack variables
DECLARE stack : ARRAY[0:9] OF INTEGER
DECLARE top : INTEGER
DECLARE maxSize : INTEGER

maxSize ← 10
top ← -1  // Empty stack

// Push operation
PROCEDURE Push(item : INTEGER)
    IF top = maxSize - 1 THEN
        OUTPUT "Stack Overflow"
    ELSE
        top ← top + 1
        stack[top] ← item
    ENDIF
ENDPROCEDURE

// Pop operation
FUNCTION Pop() RETURNS INTEGER
    DECLARE item : INTEGER
    IF top = -1 THEN
        OUTPUT "Stack Underflow"
        RETURN -1
    ELSE
        item ← stack[top]
        top ← top - 1
        RETURN item
    ENDIF
ENDFUNCTION

// Peek operation
FUNCTION Peek() RETURNS INTEGER
    IF top = -1 THEN
        OUTPUT "Stack is empty"
        RETURN -1
    ELSE
        RETURN stack[top]
    ENDIF
ENDFUNCTION

// IsEmpty
FUNCTION IsEmpty() RETURNS BOOLEAN
    RETURN top = -1
ENDFUNCTION

// IsFull
FUNCTION IsFull() RETURNS BOOLEAN
    RETURN top = maxSize - 1
ENDFUNCTION
```

**Stack Example Usage:**

```pseudocode
// Using the stack
Push(10)  // Stack: [10]
Push(20)  // Stack: [10, 20]
Push(30)  // Stack: [10, 20, 30]

OUTPUT Pop()  // Outputs 30, Stack: [10, 20]
OUTPUT Peek() // Outputs 20, Stack: [10, 20]
OUTPUT Pop()  // Outputs 20, Stack: [10]
```

---

#### **QUEUE**

**What is a Queue?**
A First-In-First-Out (FIFO) data structure. The first item added is the first to be removed (like a queue of people).

**Key Features:**
- FIFO ordering
- Add at rear, remove from front
- Two main operations: enqueue and dequeue

**Operations:**
1. **Enqueue**: Add item to rear of queue
2. **Dequeue**: Remove item from front of queue
3. **Peek/Front**: View front item without removing
4. **IsEmpty**: Check if queue is empty
5. **IsFull**: Check if queue is full

**When to Use Queues:**
- Printer job scheduling
- Task scheduling in operating systems
- Breadth-first search algorithms
- Buffering (keyboard buffer, network packets)
- Customer service systems
- Playlist management

**Types of Queue Implementation:**

**1. Linear Queue (Simple Queue):**

```pseudocode
// Queue variables
DECLARE queue : ARRAY[0:9] OF INTEGER
DECLARE front : INTEGER
DECLARE rear : INTEGER
DECLARE maxSize : INTEGER

maxSize ← 10
front ← 0
rear ← -1

// Enqueue operation
PROCEDURE Enqueue(item : INTEGER)
    IF rear = maxSize - 1 THEN
        OUTPUT "Queue Full"
    ELSE
        rear ← rear + 1
        queue[rear] ← item
    ENDIF
ENDPROCEDURE

// Dequeue operation
FUNCTION Dequeue() RETURNS INTEGER
    DECLARE item : INTEGER
    IF front > rear THEN
        OUTPUT "Queue Empty"
        RETURN -1
    ELSE
        item ← queue[front]
        front ← front + 1
        RETURN item
    ENDIF
ENDFUNCTION
```

**Problem with Linear Queue**: Wasted space at front after dequeuing.

**2. Circular Queue (Better Implementation):**

```pseudocode
// Circular queue variables
DECLARE circQueue : ARRAY[0:9] OF INTEGER
DECLARE front : INTEGER
DECLARE rear : INTEGER
DECLARE size : INTEGER
DECLARE maxSize : INTEGER

maxSize ← 10
front ← 0
rear ← -1
size ← 0

// Enqueue operation
PROCEDURE CircEnqueue(item : INTEGER)
    IF size = maxSize THEN
        OUTPUT "Queue Full"
    ELSE
        rear ← (rear + 1) MOD maxSize
        circQueue[rear] ← item
        size ← size + 1
    ENDIF
ENDPROCEDURE

// Dequeue operation
FUNCTION CircDequeue() RETURNS INTEGER
    DECLARE item : INTEGER
    IF size = 0 THEN
        OUTPUT "Queue Empty"
        RETURN -1
    ELSE
        item ← circQueue[front]
        front ← (front + 1) MOD maxSize
        size ← size - 1
        RETURN item
    ENDIF
ENDFUNCTION

// IsEmpty
FUNCTION IsEmpty() RETURNS BOOLEAN
    RETURN size = 0
ENDFUNCTION

// IsFull
FUNCTION IsFull() RETURNS BOOLEAN
    RETURN size = maxSize
ENDFUNCTION
```

---

#### **LINKED LIST**

**What is a Linked List?**
A linear data structure where elements are stored in nodes, and each node contains data and a pointer (reference) to the next node.

**Key Features:**
- Dynamic size (grows and shrinks as needed)
- Non-contiguous memory
- Each element links to the next
- Efficient insertion and deletion

**Components:**
- **Node**: Contains data and pointer to next node
- **Head**: Pointer to first node
- **Tail**: Pointer to last node (optional)
- **Null**: Indicates end of list

**Node Structure:**
```
Node:
  - Data (the actual value)
  - Next (pointer/reference to next node)
```

**Operations:**
1. **Insert at beginning**: Add node at start
2. **Insert at end**: Add node at end
3. **Insert at position**: Add node at specific position
4. **Delete**: Remove a node
5. **Search**: Find a node with specific data
6. **Traverse**: Visit all nodes

**When to Use Linked Lists:**
- Size unknown or changes frequently
- Frequent insertions/deletions needed
- Don't need random access to elements
- Memory is fragmented
- Implementing other ADTs (stacks, queues)

**Advantages:**
- Dynamic size
- Easy insertion/deletion at beginning
- No wasted memory
- Can grow as needed

**Disadvantages:**
- No random access (must traverse from start)
- Extra memory for pointers
- More complex than arrays

**Linked List Using Arrays:**

```pseudocode
// Node structure using parallel arrays
DECLARE data : ARRAY[0:9] OF INTEGER
DECLARE nextNode : ARRAY[0:9] OF INTEGER
DECLARE head : INTEGER
DECLARE free : INTEGER
DECLARE maxSize : INTEGER

maxSize ← 10
head ← -1  // Empty list
free ← 0   // First free position

// Initialize free list
PROCEDURE InitializeList()
    FOR i ← 0 TO maxSize - 2
        nextNode[i] ← i + 1
    NEXT i
    nextNode[maxSize - 1] ← -1  // End of free list
ENDPROCEDURE

// Insert at beginning
PROCEDURE InsertAtStart(value : INTEGER)
    DECLARE newNode : INTEGER
    
    IF free = -1 THEN
        OUTPUT "List Full"
    ELSE
        newNode ← free
        free ← nextNode[free]
        
        data[newNode] ← value
        nextNode[newNode] ← head
        head ← newNode
    ENDIF
ENDPROCEDURE

// Insert at end
PROCEDURE InsertAtEnd(value : INTEGER)
    DECLARE newNode : INTEGER
    DECLARE current : INTEGER
    
    IF free = -1 THEN
        OUTPUT "List Full"
    ELSE
        newNode ← free
        free ← nextNode[free]
        data[newNode] ← value
        nextNode[newNode] ← -1
        
        IF head = -1 THEN
            head ← newNode
        ELSE
            current ← head
            WHILE nextNode[current] <> -1
                current ← nextNode[current]
            ENDWHILE
            nextNode[current] ← newNode
        ENDIF
    ENDIF
ENDPROCEDURE

// Delete first node
PROCEDURE DeleteFirst()
    DECLARE temp : INTEGER
    
    IF head = -1 THEN
        OUTPUT "List Empty"
    ELSE
        temp ← head
        head ← nextNode[head]
        
        // Return to free list
        nextNode[temp] ← free
        free ← temp
    ENDIF
ENDPROCEDURE

// Search for value
FUNCTION Search(value : INTEGER) RETURNS BOOLEAN
    DECLARE current : INTEGER
    
    current ← head
    WHILE current <> -1
        IF data[current] = value THEN
            RETURN TRUE
        ENDIF
        current ← nextNode[current]
    ENDWHILE
    RETURN FALSE
ENDFUNCTION

// Display list
PROCEDURE DisplayList()
    DECLARE current : INTEGER
    
    IF head = -1 THEN
        OUTPUT "List is empty"
    ELSE
        current ← head
        WHILE current <> -1
            OUTPUT data[current], " -> "
            current ← nextNode[current]
        ENDWHILE
        OUTPUT "NULL"
    ENDIF
ENDPROCEDURE
```

**Comparison Table:**

| Feature | Stack | Queue | Linked List |
|---------|-------|-------|-------------|
| Order | LIFO | FIFO | Sequential |
| Access | Top only | Front/Rear | Any position |
| Add | Push (top) | Enqueue (rear) | Insert anywhere |
| Remove | Pop (top) | Dequeue (front) | Delete anywhere |
| Use Case | Undo, recursion | Scheduling, buffering | Dynamic data, flexible operations |

---

## 11. Programming

### 11.1 Programming Basics

#### **Declarations and Initialization**

**Constants:**
Values that cannot be changed during program execution.

```pseudocode
// Declare constants
CONSTANT PI = 3.14159
CONSTANT MAX_STUDENTS = 30
CONSTANT TAX_RATE = 0.15
CONSTANT SCHOOL_NAME = "ABC High School"

// Using constants
circumference ← 2 * PI * radius
IF numStudents > MAX_STUDENTS THEN
    OUTPUT "Class full"
ENDIF
```

**Variables:**
Named storage locations that can hold values that may change.

```pseudocode
// Declare variables
DECLARE age : INTEGER
DECLARE price : REAL
DECLARE name : STRING
DECLARE isValid : BOOLEAN

// Declare and initialize
DECLARE counter : INTEGER
counter ← 0

DECLARE total : REAL
total ← 0.0

// Multiple declarations
DECLARE x, y, z : INTEGER
DECLARE firstName, lastName : STRING
```

**Assignment:**

```pseudocode
// Simple assignment
age ← 25
name ← "John"

// Assignment with expression
total ← price * quantity
average ← sum / count

// Multiple assignments
x ← 5
y ← x + 3
z ← x * y
```

#### **Expressions**

**Arithmetic Operators:**

```pseudocode
// Addition
result ← 5 + 3        // result = 8

// Subtraction
result ← 10 - 4       // result = 6

// Multiplication
result ← 6 * 7        // result = 42

// Division (real)
result ← 15 / 2       // result = 7.5

// Integer division (DIV)
result ← 15 DIV 2     // result = 7

// Modulus (remainder)
result ← 15 MOD 2     // result = 1

// Exponentiation
result ← 2 ^ 3        // result = 8
```

**Comparison Operators:**

```pseudocode
// Equal to
IF age = 18 THEN

// Not equal to
IF age <> 18 THEN

// Greater than
IF score > 50 THEN

// Less than
IF score < 50 THEN

// Greater than or equal to
IF score >= 50 THEN

// Less than or equal to
IF score <= 50 THEN
```

**Logical Operators:**

```pseudocode
// AND - both must be true
IF age >= 18 AND hasLicense = TRUE THEN
    OUTPUT "Can drive"
ENDIF

// OR - at least one must be true
IF grade = 'A' OR grade = 'B' THEN
    OUTPUT "Good grade"
ENDIF

// NOT - reverses the condition
IF NOT isComplete THEN
    OUTPUT "Still in progress"
ENDIF

// Complex expressions
IF (score >= 40 AND attendance >= 75) OR hasExemption THEN
    OUTPUT "Eligible"
ENDIF
```

**Operator Precedence (highest to lowest):**
1. Parentheses `()`
2. Exponentiation `^`
3. Multiplication `*`, Division `/`, DIV, MOD
4. Addition `+`, Subtraction `-`
5. Comparison operators `=`, `<>`, `>`, `<`, `>=`, `<=`
6. NOT
7. AND
8. OR

#### **Input and Output**

**Input from Keyboard:**

```pseudocode
// Single input
INPUT age
INPUT name

// Input with prompt
OUTPUT "Enter your name: "
INPUT name

OUTPUT "Enter your age: "
INPUT age

// Multiple inputs
INPUT firstName
INPUT lastName
INPUT age
```

**Output to Console:**

```pseudocode
// Simple output
OUTPUT "Hello World"

// Output variable
OUTPUT name

// Output multiple items
OUTPUT "Name: ", name
OUTPUT "Age: ", age

// Output with calculation
OUTPUT "Total: ", price * quantity

// Concatenation
OUTPUT "Hello " & name & "!"
```

#### **Built-in Functions and Library Routines**

**Common Mathematical Functions:**

```pseudocode
// Square root
result ← SQRT(16)      // result = 4

// Absolute value
result ← ABS(-5)       // result = 5

// Random number (0 to 1)
result ← RANDOM()

// Random integer in range
result ← RANDOM(1, 10) // Random number 1-10

// Round to nearest integer
result ← ROUND(3.7)    // result = 4

// Round down
result ← INT(3.9)      // result = 3
```

**String Manipulation Functions:**

```pseudocode
// Length of string
len ← LENGTH("Hello")  // len = 5

// Substring (start position, length)
sub ← SUBSTRING("Hello", 1, 3)  // sub = "Hel"

// Left characters
left ← LEFT("Hello", 2)  // left = "He"

// Right characters
right ← RIGHT("Hello", 2)  // right = "lo"

// Uppercase
upper ← UCASE("hello")  // upper = "HELLO"

// Lowercase
lower ← LCASE("HELLO")  // lower = "hello"

// ASCII value of character
code ← ASC('A')  // code = 65

// Character from ASCII
char ← CHR(65)  // char = 'A'

// Convert to string
str ← STR(123)  // str = "123"

// Convert to integer
num ← INT("123")  // num = 123

// Convert to real
num ← REAL("3.14")  // num = 3.14
```

**Example Programs:**

```pseudocode
// Program to calculate circle area
CONSTANT PI = 3.14159
DECLARE radius : REAL
DECLARE area : REAL

OUTPUT "Enter radius: "
INPUT radius

area ← PI * radius ^ 2

OUTPUT "Area = ", area
```

```pseudocode
// Program to find largest of three numbers
DECLARE num1, num2, num3 : INTEGER
DECLARE largest : INTEGER

INPUT num1
INPUT num2
INPUT num3

largest ← num1

IF num2 > largest THEN
    largest ← num2
ENDIF

IF num3 > largest THEN
    largest ← num3
ENDIF

OUTPUT "Largest: ", largest
```

---

### 11.2 Constructs

#### **Selection Constructs**

**IF Statement:**

```pseudocode
// Simple IF
IF condition THEN
    // statements
ENDIF

// IF with ELSE
IF condition THEN
    // statements when true
ELSE
    // statements when false
ENDIF

// IF-ELSEIF-ELSE
IF condition1 THEN
    // statements
ELSEIF condition2 THEN
    // statements
ELSEIF condition3 THEN
    // statements
ELSE
    // statements
ENDIF
```

**Nested IF Statements:**

```pseudocode
// Grade calculator
IF score >= 70 THEN
    IF score >= 90 THEN
        grade ← 'A'
    ELSE
        IF score >= 80 THEN
            grade ← 'B'
        ELSE
            grade ← 'C'
        ENDIF
    ENDIF
ELSE
    IF score >= 50 THEN
        grade ← 'D'
    ELSE
        grade ← 'F'
    ENDIF
ENDIF
```

**CASE Statement:**
Better alternative to multiple IF-ELSEIF when checking one variable against many values.

```pseudocode
// Basic CASE structure
CASE OF variable
    value1: // statements
    value2: // statements
    value3: // statements
    OTHERWISE // statements (default)
ENDCASE

// Example: Menu selection
CASE OF choice
    1: OUTPUT "Option 1 selected"
       // Process option 1
    2: OUTPUT "Option 2 selected"
       // Process option 2
    3: OUTPUT "Option 3 selected"
       // Process option 3
    4: OUTPUT "Exit"
    OTHERWISE OUTPUT "Invalid option"
ENDCASE

// Example: Grade to description
CASE OF grade
    'A': OUTPUT "Excellent"
    'B': OUTPUT "Good"
    'C': OUTPUT "Satisfactory"
    'D': OUTPUT "Pass"
    'F': OUTPUT "Fail"
    OTHERWISE OUTPUT "Invalid grade"
ENDCASE

// Example: Day of week
CASE OF day
    1: dayName ← "Monday"
    2: dayName ← "Tuesday"
    3: dayName ← "Wednesday"
    4: dayName ← "Thursday"
    5: dayName ← "Friday"
    6: dayName ← "Saturday"
    7: dayName ← "Sunday"
    OTHERWISE dayName ← "Invalid"
ENDCASE
```

**When to Use CASE vs IF:**
- Use CASE when checking one variable against multiple specific values
- Use IF for complex conditions with AND/OR
- Use IF for range checking (e.g., score >= 50)

#### **Iteration Constructs**

**Count-Controlled Loop (FOR loop):**

```pseudocode
// Basic FOR loop
FOR counter ← startValue TO endValue
    // statements
NEXT counter

// Example: Print 1 to 10
FOR i ← 1 TO 10
    OUTPUT i
NEXT i

// FOR loop with STEP
FOR counter ← startValue TO endValue STEP increment
    // statements
NEXT counter

// Example: Even numbers 0 to 20
FOR i ← 0 TO 20 STEP 2
    OUTPUT i
NEXT i

// Example: Countdown
FOR i ← 10 TO 1 STEP -1
    OUTPUT i
NEXT i

// Nested FOR loops
FOR row ← 1 TO 5
    FOR col ← 1 TO 5
        OUTPUT "*"
    NEXT col
    OUTPUT ""  // New line
NEXT row
```

**Pre-condition Loop (WHILE loop):**
Condition checked BEFORE each iteration. May not execute at all.

```pseudocode
// Basic WHILE loop
WHILE condition DO
    // statements
ENDWHILE

// Example: Input validation
password ← ""
WHILE password <> "secret" DO
    OUTPUT "Enter password: "
    INPUT password
ENDWHILE

// Example: Sum numbers until 0 entered
total ← 0
INPUT number
WHILE number <> 0 DO
    total ← total + number
    INPUT number
ENDWHILE

// Example: Process file
OPENFILE "data.txt" FOR READ
WHILE NOT EOF("data.txt") DO
    READFILE "data.txt", line
    OUTPUT line
ENDWHILE
CLOSEFILE "data.txt"
```

**Post-condition Loop (REPEAT-UNTIL):**
Condition checked AFTER each iteration. Always executes at least once.

```pseudocode
// Basic REPEAT-UNTIL
REPEAT
    // statements
UNTIL condition

// Example: Menu system (must show menu at least once)
REPEAT
    OUTPUT "1. Add record"
    OUTPUT "2. Delete record"
    OUTPUT "3. Exit"
    INPUT choice
    
    CASE OF choice
        1: // Add record
        2: // Delete record
        3: OUTPUT "Goodbye"
    ENDCASE
UNTIL choice = 3

// Example: Input validation (must ask at least once)
REPEAT
    OUTPUT "Enter age (1-100): "
    INPUT age
UNTIL age >= 1 AND age <= 100

// Example: Calculate factorial
DECLARE n, factorial, counter : INTEGER
INPUT n
factorial ← 1
counter ← 1

REPEAT
    factorial ← factorial * counter
    counter ← counter + 1
UNTIL counter > n

OUTPUT factorial
```

#### **Choosing the Right Loop**

**Use FOR loop when:**
- Number of iterations is known in advance
- Processing array elements (all or specific range)
- Counting or incrementing by fixed amount
- Example: Print 1 to 100, process all array elements

**Use WHILE loop when:**
- Number of iterations is unknown
- Condition must be checked before first execution
- Loop might not need to execute at all
- Example: Read file until EOF, input validation

**Use REPEAT-UNTIL when:**
- Number of iterations is unknown
- Loop must execute at least once
- Condition checked at end makes more sense
- Example: Menu systems, "do-while" scenarios

**Comparison:**

```pseudocode
// FOR - known iterations
FOR i ← 1 TO 10
    OUTPUT i
NEXT i

// WHILE - may not execute
counter ← 11  // Already > 10
WHILE counter <= 10 DO
    OUTPUT counter
    counter ← counter + 1
ENDWHILE
// Nothing printed

// REPEAT - executes at least once
counter ← 11  // Already > 10
REPEAT
    OUTPUT counter
    counter ← counter + 1
UNTIL counter > 10
// Prints 11
```

---

### 11.3 Structured Programming

#### **Procedures**

**What is a Procedure?**
A named block of code that performs a specific task. It can be called multiple times from different parts of the program.

**Characteristics:**
- Performs an action (does something)
- May or may not return a value
- Can have parameters
- Promotes code reuse and modularity

**Defining a Procedure:**

```pseudocode
// Procedure without parameters
PROCEDURE ProcedureName()
    // statements
ENDPROCEDURE

// Procedure with parameters
PROCEDURE ProcedureName(parameter1 : Type, parameter2 : Type)
    // statements
ENDPROCEDURE
```

**Examples:**

```pseudocode
// Simple procedure - no parameters
PROCEDURE DisplayWelcome()
    OUTPUT "Welcome to the program"
    OUTPUT "Please follow the instructions"
ENDPROCEDURE

// Call the procedure
DisplayWelcome()

// Procedure with parameters
PROCEDURE DisplayGreeting(name : STRING, age : INTEGER)
    OUTPUT "Hello ", name
    OUTPUT "You are ", age, " years old"
ENDPROCEDURE

// Call with arguments
DisplayGreeting("Alice", 25)

// Procedure to calculate and display area
PROCEDURE DisplayRectangleArea(length : REAL, width : REAL)
    DECLARE area : REAL
    area ← length * width
    OUTPUT "Area = ", area
ENDPROCEDURE

DisplayRectangleArea(5.0, 3.0)
```

**When to Use Procedures:**
- Task performed multiple times in program
- Code needs to be organized into logical units
- Same operation needed with different data
- Complex program needs to be broken down
- Code readability needs improvement

#### **Parameters**

**Pass by Value:**
A copy of the variable's value is passed. Changes inside procedure don't affect original variable.

```pseudocode
PROCEDURE IncrementByValue(number : INTEGER)
    number ← number + 1
    OUTPUT "Inside procedure: ", number
ENDPROCEDURE

// Main program
DECLARE x : INTEGER
x ← 5
IncrementByValue(x)
OUTPUT "After procedure: ", x  // Still 5
```

**Pass by Reference:**
The memory address is passed. Changes inside procedure DO affect the original variable.

```pseudocode
PROCEDURE IncrementByReference(BYREF number : INTEGER)
    number ← number + 1
    OUTPUT "Inside procedure: ", number
ENDPROCEDURE

// Main program
DECLARE x : INTEGER
x ← 5
IncrementByReference(x)
OUTPUT "After procedure: ", x  // Now 6
```

**Multiple Parameters:**

```pseudocode
// Mix of pass by value and reference
PROCEDURE Swap(BYREF a : INTEGER, BYREF b : INTEGER)
    DECLARE temp : INTEGER
    temp ← a
    a ← b
    b ← temp
ENDPROCEDURE

// Usage
DECLARE x, y : INTEGER
x ← 10
y ← 20
OUTPUT "Before: x=", x, " y=", y
Swap(x, y)
OUTPUT "After: x=", x, " y=", y  // x=20, y=10
```

#### **Functions**

**What is a Function?**
A named block of code that performs a calculation and returns a single value.

**Characteristics:**
- Returns a value
- Used in expressions
- Can have parameters
- Must include RETURN statement

**Defining a Function:**

```pseudocode
// Function syntax
FUNCTION FunctionName(parameters) RETURNS DataType
    // statements
    RETURN value
ENDFUNCTION
```

**Examples:**

```pseudocode
// Function without parameters
FUNCTION GetPI() RETURNS REAL
    RETURN 3.14159
ENDFUNCTION

// Usage
circumference ← 2 * GetPI() * radius

// Function with parameters
FUNCTION CalculateArea(length : REAL, width : REAL) RETURNS REAL
    DECLARE area : REAL
    area ← length * width
    RETURN area
ENDFUNCTION

// Usage
rectangleArea ← CalculateArea(5.0, 3.0)
OUTPUT "Area: ", rectangleArea

// Function for validation
FUNCTION IsValidAge(age : INTEGER) RETURNS BOOLEAN
    IF age >= 0 AND age <= 120 THEN
        RETURN TRUE
    ELSE
        RETURN FALSE
    ENDIF
ENDFUNCTION

// Usage
IF IsValidAge(userAge) THEN
    OUTPUT "Valid age"
ELSE
    OUTPUT "Invalid age"
ENDIF

// Function to find maximum
FUNCTION FindMax(a : INTEGER, b : INTEGER, c : INTEGER) RETURNS INTEGER
    DECLARE max : INTEGER
    max ← a
    IF b > max THEN
        max ← b
    ENDIF
    IF c > max THEN
        max ← c
    ENDIF
    RETURN max
ENDFUNCTION

// Usage
largest ← FindMax(10, 25, 15)
```

**When to Use Functions:**
- Need to return a value
- Calculation used in expressions
- Same calculation needed multiple times
- Making code more readable

#### **Procedure vs Function**

| Aspect | Procedure | Function |
|--------|-----------|----------|
| Returns value? | No (or via reference parameters) | Yes, always |
| How called? | As a statement | In an expression |
| Purpose | Perform action | Calculate and return value |
| RETURN statement | Optional | Required |
| Example use | DisplayMenu() | CalculateTotal() |

**Examples Showing Difference:**

```pseudocode
// PROCEDURE - performs action
PROCEDURE PrintSum(a : INTEGER, b : INTEGER)
    OUTPUT "Sum is: ", a + b
ENDPROCEDURE

// Called as statement
PrintSum(5, 3)

// FUNCTION - returns value
FUNCTION CalculateSum(a : INTEGER, b : INTEGER) RETURNS INTEGER
    RETURN a + b
ENDFUNCTION

// Used in expression
total ← CalculateSum(5, 3)
OUTPUT "Sum is: ", total

// Or directly in expression
IF CalculateSum(x, y) > 100 THEN
    OUTPUT "Large sum"
ENDIF
```

#### **Terminology**

**Procedure/Function Header:**
The first line containing name, parameters, and return type (if function).

```pseudocode
FUNCTION CalculateArea(length : REAL, width : REAL) RETURNS REAL
// This is the header
```

**Procedure/Function Interface:**
The visible part (header) that shows how to use it without revealing implementation.

**Parameter:**
Variable in the procedure/function definition.

```pseudocode
PROCEDURE Example(param1 : INTEGER, param2 : STRING)
// param1 and param2 are parameters
```

**Argument:**
Actual value passed when calling the procedure/function.

```pseudocode
Example(10, "Hello")
// 10 and "Hello" are arguments
```

**Return Value:**
The value sent back by a function.

```pseudocode
FUNCTION Square(n : INTEGER) RETURNS INTEGER
    RETURN n * n  // n*n is the return value
ENDFUNCTION
```

#### **Writing Efficient Pseudocode**

**Principles:**
1. **Use meaningful names**
2. **Avoid code duplication** - use procedures/functions
3. **Keep procedures/functions focused** - one task each
4. **Use appropriate data structures**
5. **Choose efficient algorithms**
6. **Validate input early**
7. **Use early returns to avoid deep nesting**

**Example - Inefficient:**

```pseudocode
DECLARE score1, score2, score3, score4, score5 : INTEGER
INPUT score1
INPUT score2
INPUT score3
INPUT score4
INPUT score5
average ← (score1 + score2 + score3 + score4 + score5) / 5
```

**Example - Efficient:**

```pseudocode
DECLARE scores : ARRAY[0:4] OF INTEGER
DECLARE total : INTEGER

total ← 0
FOR i ← 0 TO 4
    INPUT scores[i]
    total ← total + scores[i]
NEXT i
average ← total / 5
```

**Complete Example - Student Grades System:**

```pseudocode
// Constants
CONSTANT MAX_STUDENTS = 30
CONSTANT PASS_MARK = 50

// Type definitions
TYPE Student
    DECLARE id : STRING
    DECLARE name : STRING
    DECLARE score : INTEGER
ENDTYPE

// Function to validate score
FUNCTION IsValidScore(score : INTEGER) RETURNS BOOLEAN
    RETURN score >= 0 AND score <= 100
ENDFUNCTION

// Function to determine grade
FUNCTION GetGrade(score : INTEGER) RETURNS CHAR
    IF score >= 90 THEN
        RETURN 'A'
    ELSEIF score >= 80 THEN
        RETURN 'B'
    ELSEIF score >= 70 THEN
        RETURN 'C'
    ELSEIF score >= 60 THEN
        RETURN 'D'
    ELSEIF score >= 50 THEN
        RETURN 'E'
    ELSE
        RETURN 'F'
    ENDIF
ENDFUNCTION

// Function to check if passed
FUNCTION HasPassed(score : INTEGER) RETURNS BOOLEAN
    RETURN score >= PASS_MARK
ENDFUNCTION

// Procedure to display student info
PROCEDURE DisplayStudent(s : Student)
    DECLARE grade : CHAR
    grade ← GetGrade(s.score)
    
    OUTPUT "ID: ", s.id
    OUTPUT "Name: ", s.name
    OUTPUT "Score: ", s.score
    OUTPUT "Grade: ", grade
    
    IF HasPassed(s.score) THEN
        OUTPUT "Status: PASS"
    ELSE
        OUTPUT "Status: FAIL"
    ENDIF
ENDPROCEDURE

// Main program
DECLARE students : ARRAY[0:MAX_STUDENTS-1] OF Student
DECLARE numStudents : INTEGER

INPUT numStudents

FOR i ← 0 TO numStudents - 1
    OUTPUT "Enter student ", i + 1, " details:"
    INPUT students[i].id
    INPUT students[i].name
    
    REPEAT
        INPUT students[i].score
        IF NOT IsValidScore(students[i].score) THEN
            OUTPUT "Invalid score. Enter again (0-100):"
        ENDIF
    UNTIL IsValidScore(students[i].score)
NEXT i

// Display all students
FOR i ← 0 TO numStudents - 1
    DisplayStudent(students[i])
    OUTPUT "---"
NEXT i
```

---

## 12. Software Development

### 12.1 Program Development Life Cycle

#### **Purpose of Development Life Cycle**

**What is a Development Life Cycle?**
A systematic process for planning, creating, testing, and deploying software systems.

**Why Use a Development Life Cycle?**
- Provides structured approach
- Ensures all stages are completed
- Improves project management
- Reduces risk of failure
- Better quality software
- Clear milestones and deliverables
- Easier to track progress

**Need for Different Life Cycles:**
Different projects have different requirements:
- Size and complexity
- Budget and timeline
- User involvement needed
- Clarity of requirements
- Risk tolerance
- Need for flexibility

---

#### **Types of Development Life Cycles**

### **1. Waterfall Model**

**Description:**
Sequential approach where each phase must be completed before the next begins. Like a waterfall flowing downward.

**Phases:**
1. Requirements Analysis
2. System Design
3. Implementation (Coding)
4. Testing
5. Deployment
6. Maintenance

**Characteristics:**
- Linear and sequential
- No going back to previous phase
- Each phase has specific deliverables
- Documentation-heavy
- Plan-driven

**Principles:**
- Complete one phase fully before next
- Clear documentation at each stage
- Progress flows in one direction
- Changes difficult once phase complete

**Benefits:**
- Simple and easy to understand
- Easy to manage (clear stages)
- Works well for small projects
- Clear milestones
- Good documentation
- Easy to measure progress
- Suitable when requirements are clear and stable

**Drawbacks:**
- Inflexible - hard to make changes
- Testing happens late
- Working software produced late
- Not suitable for complex projects
- Risk of not meeting user needs
- Poor for unclear requirements
- Customer sees product only at end

**Best Used For:**
- Small, simple projects
- Well-understood requirements
- Stable technology
- Short projects
- Projects with fixed requirements

**Example Scenario:**
Creating a simple payroll system with clearly defined requirements that won't change.

---

### **2. Iterative Model**

**Description:**
Development through repeated cycles (iterations). Each iteration produces a working version with more features.

**Process:**
1. Plan iteration
2. Design for iteration
3. Implement features
4. Test iteration
5. Evaluate and get feedback
6. Repeat with next iteration

**Characteristics:**
- Repeated cycles
- Each iteration builds on previous
- Working software produced early
- Regular feedback
- Incremental development

**Principles:**
- Start with core functionality
- Add features in iterations
- Each iteration is mini-waterfall
- Regular testing and feedback
- Continuous improvement

**Benefits:**
- Working software produced early
- Regular user feedback
- Can change requirements between iterations
- Risks identified early
- Easier to test and debug
- Parallel development possible
- Progress visible to stakeholders

**Drawbacks:**
- Requires good planning
- More management overhead
- Requires more resources
- Can be time-consuming
- Architecture decisions needed early
- Risk of scope creep

**Best Used For:**
- Large projects
- Unclear or evolving requirements
- Complex systems
- Projects where early delivery needed
- Projects needing user feedback

**Example Scenario:**
Developing a school management system where basic features (student records) are delivered first, then attendance, then grades, etc.

---

### **3. Rapid Application Development (RAD)**

**Description:**
Fast development using prototypes, user feedback, and reusable components. Emphasis on quick delivery over perfect planning.

**Phases:**
1. Requirements Planning (brief)
2. User Design (workshops with users)
3. Construction (rapid prototyping)
4. Cutover (testing, training, deployment)

**Characteristics:**
- Very fast development
- Heavy user involvement
- Prototyping-focused
- Uses reusable components/tools
- Minimal planning
- Time-boxed iterations

**Principles:**
- Speed over perfection
- User involvement throughout
- Prototype quickly, get feedback
- Reuse components where possible
- Small focused teams
- Iterative refinement

**Benefits:**
- Very fast development
- High user involvement
- Quick feedback
- Reduced development time
- Lower costs
- Encourages reusability
- Flexibility to changes
- Early problem identification

**Drawbacks:**
- Requires skilled developers
- Needs committed users
- Not suitable for all projects
- May sacrifice quality for speed
- Requires powerful development tools
- Not suitable for large teams
- May lack proper documentation
- System performance might suffer

**Best Used For:**
- Time-critical projects
- Projects needing quick delivery
- Clear user availability
- Systems that can be modularized
- Small to medium projects

**Example Scenario:**
Creating a prototype mobile app for a startup that needs to test market quickly.

---

**Comparison Table:**

| Aspect | Waterfall | Iterative | RAD |
|--------|-----------|-----------|-----|
| Flexibility | Low | Medium | High |
| User Involvement | Low (mainly at start/end) | Medium (at iterations) | Very High (continuous) |
| Development Speed | Slow | Medium | Very Fast |
| Documentation | Heavy | Medium | Light |
| Cost | High (if changes needed) | Medium | Low to Medium |
| Risk | High (late testing) | Medium (regular reviews) | Low (early feedback) |
| Requirements | Must be clear upfront | Can evolve | Can be unclear initially |
| Team Size | Any | Medium to Large | Small |
| Best For | Simple, stable projects | Complex projects | Quick prototypes |

---

#### **Stages in Program Development Life Cycle**

### **1. Analysis Stage**

**Purpose:**
Understand the problem and determine what the system needs to do.

**Activities:**
- Identify the problem
- Gather requirements from stakeholders
- Study current system (if exists)
- Determine feasibility (technical, economic, operational)
- Define system boundaries
- Identify inputs, processes, outputs
- Create requirements specification document

**Key Questions:**
- What problem needs solving?
- Who are the users?
- What are the functional requirements?
- What are the non-functional requirements?
- What constraints exist?
- What data is needed?

**Techniques:**
- Interviews with users
- Questionnaires/surveys
- Observation of current system
- Document analysis
- Workshops

**Outputs:**
- Requirements specification
- Feasibility report
- System objectives
- User requirements document

**Example:**
*For a library system:*
- Interview librarians about current processes
- Observe how books are issued/returned
- Identify requirements: search books, issue books, track returns, manage members
- Determine data needed: book details, member details, transaction records

---

### **2. Design Stage**

**Purpose:**
Plan HOW the system will work and be built.

**Activities:**
- Design system architecture
- Design data structures
- Design algorithms
- Design user interface
- Create design documentation
- Plan module structure
- Define file formats
- Design database schema (if applicable)

**Design Types:**

**High-Level Design:**
- Overall system structure
- Module breakdown
- Data flow between modules
- System architecture

**Low-Level Design:**
- Detailed algorithm design
- Data structure specifications
- Pseudocode for each module
- Interface specifications

**Outputs:**
- System flowcharts
- Structure charts
- Pseudocode
- Data dictionaries
- Screen layouts/mockups
- File/database designs
- Algorithm specifications

**Example:**
*For library system:*
- Design structure: Login module, Search module, Issue module, Return module
- Design data structures: Book record, Member record, Transaction record
- Design algorithms: Search algorithm, fine calculation algorithm
- Design UI: Main menu, search screen, issue form

---

### **3. Coding/Implementation Stage**

**Purpose:**
Write the actual program code based on the design.

**Activities:**
- Select programming language
- Write code for each module
- Follow coding standards
- Comment code appropriately
- Create user documentation
- Set up development environment
- Version control

**Best Practices:**
- Use meaningful variable names
- Write modular code
- Add comments
- Follow style guidelines
- Use version control (Git)
- Write code incrementally
- Test as you code

**Outputs:**
- Source code files
- Executable programs
- Code documentation
- User manuals
- Technical documentation

**Example:**
```pseudocode
// Implement search book function
FUNCTION SearchBook(isbn : STRING) RETURNS Book
    DECLARE found : BOOLEAN
    DECLARE i : INTEGER
    
    found ← FALSE
    FOR i ← 0 TO numBooks - 1
        IF books[i].isbn = isbn THEN
            found ← TRUE
            RETURN books[i]
        ENDIF
    NEXT i
    
    IF NOT found THEN
        OUTPUT "Book not found"
    ENDIF
ENDFUNCTION
```

---

### **4. Testing Stage**

**Purpose:**
Ensure the program works correctly and meets requirements.

**Activities:**
- Create test plan
- Design test cases
- Execute tests
- Record results
- Fix bugs
- Retest (regression testing)
- Validate against requirements

**Types of Testing:**
(Covered in detail in section 12.3)

**Outputs:**
- Test plan
- Test cases
- Test results/logs
- Bug reports
- Corrected code

---

### **5. Maintenance Stage**

**Purpose:**
Keep the system working and improve it after deployment.

**Activities:**
- Fix bugs discovered by users
- Make updates and improvements
- Adapt to changing requirements
- Optimize performance
- Update documentation

**Types of Maintenance:**

**1. Corrective Maintenance:**
- Fix bugs and errors
- Correct logic errors
- Fix calculation mistakes

**2. Adaptive Maintenance:**
- Adapt to new environment
- Update for new OS version
- Modify for new hardware
- Comply with new regulations

**3. Perfective Maintenance:**
- Improve performance
- Add new features
- Enhance user interface
- Optimize code

**Importance:**
- Systems need ongoing support
- Requirements change over time
- Technology evolves
- Users discover issues
- New features requested

**Example:**
*Library system maintenance:*
- Corrective: Fix bug in fine calculation
- Adaptive: Update for new operating system
- Perfective: Add email notification feature

---

## 12.2 Program Design

### **Structure Charts**

#### **What is a Structure Chart?**

A structure chart is a diagram showing the hierarchical breakdown of a system into modules, and the data passed between them.

**Purpose:**
- Show modular structure of program
- Illustrate relationships between modules
- Show data flow between modules
- Help plan program structure
- Document system design

**Components:**

**1. Module (Rectangle):**
```
┌─────────────┐
│  Module     │
│  Name       │
└─────────────┘
```

**2. Module Call (Vertical Line with Arrow):**
Shows one module calling another.

**3. Data Couple (Arrow with circle):**
Data passed between modules.
- Arrow pointing down: Data passed TO called module (parameter)
- Arrow pointing up: Data returned FROM called module (return value)

**4. Control Couple (Arrow with filled circle):**
Control information passed (flags, status codes).

**Notation:**
```
      ┌─────────────┐
      │   Main      │
      │  Program    │
      └─────────────┘
            │
        ↓ data1
            │
      ┌─────────────┐
      │  Process    │
      │   Data      │
      └─────────────┘
            │
        ↑ result
```

#### **Creating Structure Charts**

**Steps:**
1. Identify main program/module
2. Break down into sub-modules
3. Continue decomposing until modules are simple
4. Show data flow between modules
5. Label all data couples

**Example: Student Grades System**

```
                    ┌──────────────────┐
                    │  Student Grades  │
                    │  System (Main)   │
                    └──────────────────┘
                             │
           ┌─────────────────┼─────────────────┐
           │                 │                 │
      studentData       studentData       studentData
           ↓                 ↓                 ↓
    ┌──────────┐      ┌──────────┐     ┌──────────┐
    │  Input   │      │ Calculate│     │  Display │
    │  Data    │      │  Grade   │     │  Results │
    └──────────┘      └──────────┘     └──────────┘
           │                 │
       student           score
           ↑                 ↓
                             │
                          grade
                             ↑
```

**Structure Chart with Detail:**

```
                    ┌──────────────────┐
                    │   Library        │
                    │   System         │
                    └──────────────────┘
                             │
           ┌─────────────────┼─────────────────┬─────────────┐
           │                 │                 │             │
        choice            bookData          memberData     status
           ↓                 ↓                 ↓             ↓
    ┌──────────┐      ┌──────────┐     ┌──────────┐  ┌──────────┐
    │  Display │      │  Manage  │     │  Manage  │  │  Issue   │
    │   Menu   │      │  Books   │     │ Members  │  │  Book    │
    └──────────┘      └──────────┘     └──────────┘  └──────────┘
                             │                 │
                    ┌────────┼────────┐       │
                    │                 │       │
                isbn, title        isbn    memberId
                    ↓                 ↓       ↓
              ┌──────────┐      ┌──────────┐
              │   Add    │      │  Search  │
              │   Book   │      │   Book   │
              └──────────┘      └──────────┘
                                      │
                                   found
                                      ↑
```

#### **Deriving Pseudocode from Structure Chart**

**Process:**
1. Start with main module
2. Create procedure/function for each module
3. Add parameters based on data couples
4. Implement calls to sub-modules
5. Add logic for processing

**Example:**

From this structure:
```
       Main
         │
      name, score
         ↓
    Calculate Grade
         │
      grade
         ↑
```

**Derived Pseudocode:**

```pseudocode
// Main Program
DECLARE studentName : STRING
DECLARE studentScore : INTEGER
DECLARE finalGrade : CHAR

INPUT studentName
INPUT studentScore

finalGrade ← CalculateGrade(studentScore)

OUTPUT studentName, " got grade ", finalGrade

// Calculate Grade Function
FUNCTION CalculateGrade(score : INTEGER) RETURNS CHAR
    DECLARE grade : CHAR
    
    IF score >= 90 THEN
        grade ← 'A'
    ELSEIF score >= 80 THEN
        grade ← 'B'
    ELSEIF score >= 70 THEN
        grade ← 'C'
    ELSEIF score >= 60 THEN
        grade ← 'D'
    ELSE
        grade ← 'F'
    ENDIF
    
    RETURN grade
ENDFUNCTION
```

**Complex Example:**

Structure Chart:
```
                Main Program
                     │
        ┌────────────┼────────────┐
        │            │            │
     students    students      students
        ↓            ↓            ↓
   InputStudents  ProcessScores  DisplayResults
        │            │
    students      students
        ↑            │
                  average
                     ↑
```

**Pseudocode:**

```pseudocode
// Type definition
TYPE Student
    DECLARE name : STRING
    DECLARE score : INTEGER
ENDTYPE

// Main Program
DECLARE students : ARRAY[0:29] OF Student
DECLARE numStudents : INTEGER
DECLARE classAverage : REAL

InputStudents(students, numStudents)
classAverage ← ProcessScores(students, numStudents)
DisplayResults(students, numStudents, classAverage)

// Input Students Procedure
PROCEDURE InputStudents(BYREF students : ARRAY OF Student, 
                        BYREF count : INTEGER)
    INPUT count
    FOR i ← 0 TO count - 1
        OUTPUT "Enter student ", i + 1, " name:"
        INPUT students[i].name
        OUTPUT "Enter score:"
        INPUT students[i].score
    NEXT i
ENDPROCEDURE

// Process Scores Function
FUNCTION ProcessScores(students : ARRAY OF Student, 
                       count : INTEGER) RETURNS REAL
    DECLARE total : INTEGER
    DECLARE average : REAL
    
    total ← 0
    FOR i ← 0 TO count - 1
        total ← total + students[i].score
    NEXT i
    
    average ← total / count
    RETURN average
ENDFUNCTION

// Display Results Procedure
PROCEDURE DisplayResults(students : ARRAY OF Student,
                        count : INTEGER,
                        average : REAL)
    OUTPUT "Class Results:"
    OUTPUT "=============="
    
    FOR i ← 0 TO count - 1
        OUTPUT students[i].name, ": ", students[i].score
    NEXT i
    
    OUTPUT ""
    OUTPUT "Class Average: ", average
ENDPROCEDURE
```

---

### **State-Transition Diagrams**

#### **What is a State-Transition Diagram?**

A diagram showing the different states a system can be in and how it transitions between states based on events/conditions.

**Purpose:**
- Document system behavior
- Show how system responds to events
- Illustrate state changes
- Help design event-driven systems
- Validate system logic

**Components:**

**1. State (Circle or Rounded Rectangle):**
A condition or situation the system is in.

**2. Transition (Arrow):**
Movement from one state to another.

**3. Event/Condition (Label on Arrow):**
What causes the transition.

**4. Initial State (Circle with arrow pointing to it):**
Starting state.

**5. Final State (Double circle):**
Ending state.

**Notation:**
```
    [Initial]
        │
        │ event1
        ↓
    ┌────────┐
    │ State1 │
    └────────┘
        │
        │ event2
        ↓
    ┌────────┐
    │ State2 │
    └────────┘
        │
        │ event3
        ↓
    ((Final))
```

#### **Examples:**

**Example 1: Traffic Light System**

```
      [Start]
         │
         ↓
     ┌──────┐
     │ Red  │←──────────────┐
     └──────┘               │
         │                  │
         │ 30 seconds       │
         ↓                  │
     ┌──────┐               │
     │Green │               │
     └──────┘               │
         │                  │
         │ 25 seconds       │
         ↓                  │
     ┌──────┐               │
     │Amber │               │
     └──────┘               │
         │                  │
         │ 5 seconds        │
         └──────────────────┘
```

**Example 2: ATM Machine**

```
       [Start]
          │
          │ Card Inserted
          ↓
     ┌──────────┐
     │ Waiting  │←─────────┐
     │ for PIN  │          │
     └──────────┘          │
          │                │
          │ PIN Entered    │ Cancel
          ↓                │
     ┌──────────┐          │
     │Validating│          │
     │   PIN    │          │
     └──────────┘          │
          │                │
     ┌────┴────┐           │
     │         │           │
Valid PIN   Invalid PIN    │
     │         │           │
     ↓         ↓           │
┌─────────┐ ┌──────┐      │
│  Menu   │ │Locked│      │
│Selection│ └──────┘      │
└─────────┘               │
     │                    │
     │ Withdraw           │
     ↓                    │
┌─────────┐               │
│Processing               │
│Transaction│             │
└─────────┘               │
     │                    │
     │ Complete           │
     ↓                    │
┌─────────┐               │
│Dispensing               │
│  Cash   │               │
└─────────┘               │
     │                    │
     │ Cash Taken         │
     └────────────────────┘
```

**Example 3: Online Order System**

```
        [Start]
           │
           │ Place Order
           ↓
      ┌─────────┐
      │ Pending │
      └─────────┘
           │
      ┌────┴────┐
      │         │
  Payment    Cancel
   Received      │
      │         ↓
      ↓    ┌──────────┐
  ┌─────────┐│Cancelled │
  │Confirmed││          │
  └─────────┘└──────────┘
      │          │
      │ Shipped  │
      ↓          │
  ┌─────────┐   │
  │Shipped  │   │
  └─────────┘   │
      │         │
      │Delivered│
      ↓         │
  ┌─────────┐  │
  │Delivered│  │
  └─────────┘  │
      │        │
      └────┬───┘
           │
           ↓
       ((End))
```

**Example 4: User Login System**

```
       [Start]
          │
          │ Request Login
          ↓
     ┌──────────┐
     │  Logged  │
     │   Out    │
     └──────────┘
          │
          │ Enter Credentials
          ↓
     ┌──────────┐
     │Validating│
     └──────────┘
          │
     ┌────┴─────┐
     │          │
Valid Creds  Invalid
     │          │
     ↓          ↓
┌─────────┐ ┌──────────┐
│ Logged  │ │ Failed   │
│   In    │ │ Attempt  │
└─────────┘ └──────────┘
     │          │
     │          │ Retry (< 3 attempts)
     │          └────────────────┐
     │                           │
     │          │ 3rd Failed     │
     │          ↓                │
     │      ┌──────────┐        │
     │      │ Locked   │        │
     │      └──────────┘        │
     │                          │
     │ Logout                   │
     └──────────────────────────┘
```

**Implementing State-Transition Logic:**

```pseudocode
// ATM System Example

TYPE ATMState = (WAITING_CARD, WAITING_PIN, VALIDATING, 
                 MENU, PROCESSING, LOCKED)

DECLARE currentState : ATMState
DECLARE pinAttempts : INTEGER

currentState ← WAITING_CARD
pinAttempts ← 0

REPEAT
    CASE OF currentState
        WAITING_CARD:
            OUTPUT "Please insert card"
            IF cardInserted THEN
                currentState ← WAITING_PIN
            ENDIF
            
        WAITING_PIN:
            OUTPUT "Enter PIN"
            INPUT pin
            currentState ← VALIDATING
            
        VALIDATING:
            IF ValidatePin(pin) THEN
                currentState ← MENU
                pinAttempts ← 0
            ELSE
                pinAttempts ← pinAttempts + 1
                IF pinAttempts >= 3 THEN
                    currentState ← LOCKED
                ELSE
                    OUTPUT "Invalid PIN. Try again"
                    currentState ← WAITING_PIN
                ENDIF
            ENDIF
            
        MENU:
            DisplayMenu()
            INPUT choice
            IF choice = "withdraw" THEN
                currentState ← PROCESSING
            ELSEIF choice = "cancel" THEN
                currentState ← WAITING_CARD
            ENDIF
            
        PROCESSING:
            ProcessTransaction()
            currentState ← MENU
            
        LOCKED:
            OUTPUT "Card locked. Contact bank"
            EjectCard()
            currentState ← WAITING_CARD
    ENDCASE
UNTIL userExits
```

---

## 12.3 Program Testing and Maintenance

### **Types of Errors**

#### **1. Syntax Errors**

**Definition:**
Mistakes in the code that violate the programming language's rules.

**Characteristics:**
- Detected by compiler/interpreter
- Prevent program from running
- Easy to identify (usually with error message)
- Must be fixed before execution

**Examples:**
```pseudocode
// Missing ENDIF
IF x > 10 THEN
    OUTPUT "Large"
// Error: Expected ENDIF

// Incorrect operator
x ← 5 == 3
// Error: Should use = not ==

// Misspelled keyword
DELCARE age : INTEGER
// Error: Should be DECLARE

// Missing quotation marks
OUTPUT "Hello
// Error: Unclosed string

// Incorrect loop syntax
FOR i ← 1 TO 10
    OUTPUT i
// Error: Missing NEXT i
```

**How to Fix:**
- Read error messages carefully
- Check spelling of keywords
- Verify syntax rules
- Use IDE with syntax highlighting
- Check matching brackets/quotes

---

#### **2. Logic Errors**

**Definition:**
Program runs but produces incorrect results due to flawed algorithm or logic.

**Characteristics:**
- No error messages produced
- Program executes completely
- Results are wrong
- Hardest to find and fix
- Requires careful testing

**Examples:**

```pseudocode
// Wrong: Using < instead of <=
IF score < 50 THEN  // Should be score >= 50
    OUTPUT "Pass"
ELSE
    OUTPUT "Fail"
ENDIF
// Score of 50 incorrectly classified as fail

// Wrong: Incorrect formula
area ← length + width  // Should be length * width

// Wrong: Loop boundary
total ← 0
FOR i ← 0 TO 9  // Should be 0 TO 10 for 10 items
    total ← total + numbers[i]
NEXT i

// Wrong: Initialization
counter ← 1  // Should be 0
FOR i ← 0 TO 9
    counter ← counter + 1
NEXT i
// Counter will be 11 instead of 10

// Wrong: Order of operations
average ← total / count * 100  // Should be (total / count) * 100
```

**How to Find:**
- Dry running (trace tables)
- Test with different data
- Check against expected results
- Use debugging tools
- Review algorithm logic

---

#### **3. Run-time Errors**

**Definition:**
Errors that occur during program execution, causing the program to crash or behave unexpectedly.

**Characteristics:**
- Occur while program is running
- May cause program to crash
- Often related to external factors
- Can be handled with error checking

**Examples:**

```pseudocode
// Division by zero
result ← 10 / 0
// Error: Division by zero

// Array index out of bounds
DECLARE numbers : ARRAY[0:9] OF INTEGER
value ← numbers[15]
// Error: Index 15 doesn't exist

// File not found
OPENFILE "data.txt" FOR READ
// Error: If file doesn't exist

// Invalid type conversion
number ← INT("abc")
// Error: Cannot convert "abc" to integer

// Infinite recursion
FUNCTION Factorial(n : INTEGER) RETURNS INTEGER
    RETURN n * Factorial(n - 1)  // Missing base case
ENDFUNCTION
// Error: Stack overflow

// Null pointer/uninitialized variable
DECLARE name : STRING
length ← LENGTH(name)
// Error: name not initialized
```

**How to Prevent:**
- Validate input data
- Check array bounds
- Verify file existence
- Handle exceptions
- Test edge cases
- Add defensive programming

**Defensive Programming Example:**

```pseudocode
// Safe division
FUNCTION SafeDivide(a : REAL, b : REAL) RETURNS REAL
    IF b = 0 THEN
        OUTPUT "Error: Division by zero"
        RETURN 0
    ELSE
        RETURN a / b
    ENDIF
ENDFUNCTION

// Safe array access
FUNCTION GetArrayElement(arr : ARRAY OF INTEGER, 
                         index : INTEGER) RETURNS INTEGER
    IF index >= 0 AND index < LENGTH(arr) THEN
        RETURN arr[index]
    ELSE
        OUTPUT "Error: Invalid index"
        RETURN -1
    ENDIF
ENDFUNCTION
```

---

### **Correcting Errors**

**Process:**
1. **Identify** the error (error message, testing, observation)
2. **Locate** the error in code (line number, debugging)
3. **Understand** why it's wrong (trace logic, review algorithm)
4. **Fix** the error (correct code)
5. **Test** the fix (verify it works)
6. **Regression test** (ensure fix didn't break anything else)

**Example:**

```pseudocode
// Original (with logic error)
DECLARE numbers : ARRAY[0:9] OF INTEGER
DECLARE total, average : REAL

total ← 0
FOR i ← 1 TO 10  // Logic error: should start at 0
    total ← total + numbers[i]
NEXT i
average ← total / 10

// Corrected
total ← 0
FOR i ← 0 TO 9  // Fixed: correct array bounds
    total ← total + numbers[i]
NEXT i
average ← total / 10
```

---

### **Methods of Testing**

#### **1. Dry Run (Trace Table)**

**Definition:**
Manually working through the algorithm step-by-step, recording variable values in a table.

**Purpose:**
- Find logic errors
- Understand algorithm flow
- Verify correctness before coding
- Educational tool

**How to Create:**
1. Draw table with columns for variables and output
2. Add row for each step/iteration
3. Update values as algorithm executes
4. Record output when produced

**Example:**

```pseudocode
total ← 0
FOR i ← 1 TO 3
    INPUT number
    total ← total + number
NEXT i
OUTPUT total
```

**Trace Table:**

| Step | i | number (INPUT) | total | OUTPUT |
|------|---|----------------|-------|--------|
| 1    | - | -              | 0     | -      |
| 2    | 1 | 5              | 5     | -      |
| 3    | 2 | 10             | 15    | -      |
| 4    | 3 | 3              | 18    | -      |
| 5    | - | -              | 18    | 18     |

**Complex Example:**

```pseudocode
DECLARE numbers : ARRAY[0:4] OF INTEGER
numbers[0] ← 3
numbers[1] ← 7
numbers[2] ← 2
numbers[3] ← 9
numbers[4] ← 5

max ← numbers[0]
FOR i ← 1 TO 4
    IF numbers[i] > max THEN
        max ← numbers[i]
    ENDIF
NEXT i
OUTPUT max
```

**Trace Table:**

| Step | i | numbers[i] | max | Condition (numbers[i] > max) | OUTPUT |
|------|---|------------|-----|------------------------------|--------|
| 1    | - | -          | 3   | -                            | -      |
| 2    | 1 | 7          | 7   | TRUE (7 > 3)                 | -      |
| 3    | 2 | 2          | 7   | FALSE (2 > 7)                | -      |
| 4    | 3 | 9          | 9   | TRUE (9 > 7)                 | -      |
| 5    | 4 | 5          | 9   | FALSE (5 > 9)                | -      |
| 6    | - | -          | 9   | -                            | 9      |

---

#### **2. Walkthrough**

**Definition:**
A manual review where developers walk through the code line-by-line with team members.

**Purpose:**
- Find errors before testing
- Share knowledge
- Improve code quality
- Get feedback

**Process:**
1. Developer presents code to team
2. Team reviews logic and design
3. Questions asked and answered
4. Issues identified and noted
5. Improvements suggested

**Benefits:**
- Early error detection
- Knowledge sharing
- Better code quality
- Team collaboration

---

#### **3. White-Box Testing**

**Definition:**
Testing based on knowledge of internal code structure. Tests all paths, branches, and conditions.

**Also Known As:**
- Structural testing
- Glass-box testing
- Clear-box testing

**What is Tested:**
- All code paths executed
- All branches (IF/ELSE) covered
- All loops tested
- Internal logic verified

**Techniques:**
- Statement coverage (every line executed)
- Branch coverage (every IF/ELSE path tested)
- Path coverage (all possible paths through code)

**Example:**

```pseudocode
FUNCTION CheckAge(age : INTEGER) RETURNS STRING
    IF age < 0 THEN
        RETURN "Invalid"
    ELSEIF age < 18 THEN
        RETURN "Minor"
    ELSEIF age < 65 THEN
        RETURN "Adult"
    ELSE
        RETURN "Senior"
    ENDIF
ENDFUNCTION
```

**White-Box Test Cases:**
- Test age = -1 (first branch)
- Test age = 10 (second branch)
- Test age = 30 (third branch)
- Test age = 70 (else branch)
- Test age = 0, 18, 65 (boundaries)

---

#### **4. Black-Box Testing**

**Definition:**
Testing based on requirements/specifications without knowledge of internal code.

**Also Known As:**
- Functional testing
- Specification-based testing

**What is Tested:**
- Inputs produce correct outputs
- System meets requirements
- User interface works correctly
- System behaves as specified

**Focus:**
- What the system does
- Not how it does it
- User perspective

**Example:**

For a calculator program:
- Test: 5 + 3 = 8 (correct output?)
- Test: 10 / 2 = 5 (correct output?)
- Test: 10 / 0 (error handling?)
- Don't care about internal algorithm

---

#### **5. Integration Testing**

**Definition:**
Testing how different modules work together when combined.

**Purpose:**
- Verify modules interface correctly
- Test data flow between modules
- Find integration issues

**Approaches:**

**Big Bang:**
- Combine all modules at once
- Test complete system
- Hard to locate errors

**Incremental:**
- Add modules one at a time
- Test after each addition
- Easier to find errors

**Top-Down:**
- Start with main module
- Add sub-modules progressively
- Use stubs for missing modules

**Bottom-Up:**
- Start with lowest modules
- Build up to main module
- Use drivers to test

**Example:**
Testing a library system:
1. Test book module alone
2. Test member module alone
3. Integrate and test book + member modules
4. Add transaction module
5. Test all three together

---

#### **6. Alpha Testing**

**Definition:**
Testing by internal staff before release to external users.

**Characteristics:**
- Done by developers/testers
- In controlled environment
- Before beta release
- Finds major bugs

**Purpose:**
- Identify obvious bugs
- Verify basic functionality
- Prepare for beta testing

---

#### **7. Beta Testing**

**Definition:**
Testing by real users in real environment before final release.

**Characteristics:**
- Done by selected external users
- In real-world conditions
- Provides user feedback
- Identifies usability issues

**Purpose:**
- Real-world testing
- User feedback
- Find unexpected issues
- Validate user experience

**Example:**
- Software company releases beta version
- Users test for 30 days
- Report bugs and suggestions
- Company fixes issues before final release

---

#### **8. Acceptance Testing**

**Definition:**
Final testing to verify system meets business requirements and is ready for deployment.

**Characteristics:**
- Done by client/customer
- Based on requirements
- Determines if system is accepted
- Final check before deployment

**Types:**

**User Acceptance Testing (UAT):**
- End users test system
- Verify it meets their needs
- Real business scenarios

**Operational Acceptance Testing:**
- Test backup/recovery
- Check maintenance procedures
- Verify documentation

**Purpose:**
- Final validation
- Customer approval
- Go/no-go decision

---

#### **9. Stub Testing**

**Definition:**
Using temporary placeholder code (stubs) to test modules that depend on other modules not yet developed.

**What is a Stub?**
A simplified dummy module that simulates the behavior of a real module.

**Purpose:**
- Test top-level modules before lower modules ready
- Continue development in parallel
- Isolate testing

**Example:**

```pseudocode
// Real function (not yet developed)
FUNCTION CalculateDiscount(price : REAL, customerType : STRING) 
    RETURNS REAL
    // Complex calculation logic
    // Not implemented yet
ENDFUNCTION

// Stub version for testing
FUNCTION CalculateDiscount(price : REAL, customerType : STRING) 
    RETURNS REAL
    // Simplified stub - returns fixed value
    RETURN price * 0.1  // Always 10% discount
ENDFUNCTION

// Main program can be tested with stub
DECLARE totalPrice : REAL
DECLARE discount : REAL

totalPrice ← 100.0
discount ← CalculateDiscount(totalPrice, "regular")
OUTPUT "Discount: ", discount
```

---

### **Test Strategy and Test Plan**

#### **Test Strategy**

**Definition:**
High-level approach to testing that defines overall testing goals and methods.

**Components:**
- Testing objectives
- Testing scope (what to test)
- Testing approach (methods to use)
- Resources needed
- Schedule
- Entry and exit criteria
- Risk assessment

**Example Test Strategy Elements:**
- Unit testing by developers
- Integration testing by QA team
- User acceptance testing by client
- Automated regression testing
- Performance testing for critical functions

**Need for Test Strategy:**
- Provides direction for testing
- Ensures comprehensive coverage
- Allocates resources effectively
- Manages risks
- Sets quality standards

---

#### **Test Plan**

**Definition:**
Detailed document describing specific tests to be performed, test data, expected results, and procedures.

**Contents of a Test Plan:**

1. **Test Objectives**
   - What is being tested
   - Purpose of each test

2. **Test Scope**
   - Features to be tested
   - Features not to be tested

3. **Test Cases**
   - Specific inputs
   - Expected outputs
   - Test procedures

4. **Test Data**
   - Normal data
   - Abnormal data
   - Boundary data

5. **Test Schedule**
   - When tests will run
   - Duration
   - Milestones

6. **Resources**
   - Personnel
   - Hardware/software needed
   - Budget

7. **Test Environment**
   - Hardware specifications
   - Software versions
   - Network setup

8. **Responsibilities**
   - Who performs each test
   - Who reviews results

9. **Exit Criteria**
   - When testing is complete
   - Acceptable pass rate

**Example Test Plan Section:**

```
Test Plan: Library Management System
====================================

Test Case ID: TC001
Module: Book Search
Description: Test search by ISBN

Pre-conditions:
- Database contains test books
- User is logged in

Test Steps:
1. Navigate to search page
2. Enter ISBN: "978-0-123456-78-9"
3. Click Search button

Test Data: ISBN = "978-0-123456-78-9"
Expected Result: Book details displayed
Actual Result: [To be filled during testing]
Status: [Pass/Fail]
Tester: John Smith
Date: [Test date]
```

**Why Test Plans are Important:**
- Ensures systematic testing
- Provides documentation
- Tracks testing progress
- Enables repeatable tests
- Facilitates communication
- Proves due diligence

---

### **Test Data Types**

#### **1. Normal (Valid) Data**

**Definition:**
Typical, valid data that the system should handle correctly in everyday use.

**Purpose:**
- Verify system works under normal conditions
- Test standard functionality
- Ensure expected operations succeed

**Examples:**

For age input (valid range 0-120):
- Normal: 25, 45, 70

For email validation:
- Normal: "user@example.com", "john.smith@company.co.uk"

For grade input (A-F):
- Normal: 'B', 'C', 'D'

**Test Case Example:**

```pseudocode
// Function to test
FUNCTION CalculateDiscount(price : REAL) RETURNS REAL
    IF price >= 100 THEN
        RETURN price * 0.1
    ELSE
        RETURN 0
    ENDIF
ENDFUNCTION

// Normal test data
Test 1: price = 150 → Expected: 15.0
Test 2: price = 200 → Expected: 20.0
Test 3: price = 50 → Expected: 0
```

---

#### **2. Abnormal (Invalid/Erroneous) Data**

**Definition:**
Invalid data that should be rejected or cause error messages.

**Purpose:**
- Test error handling
- Verify validation works
- Ensure system doesn't crash
- Check appropriate error messages

**Examples:**

For age input (valid range 0-120):
- Abnormal: -5, 150, "abc", blank

For email validation:
- Abnormal: "notanemail", "missing@", "@nodomain.com"

For grade input (A-F):
- Abnormal: 'G', 'Z', '5', "AB"

For numeric calculation:
- Abnormal: Letters instead of numbers, special characters

**Test Case Example:**

```pseudocode
// Function with validation
FUNCTION GetAge() RETURNS INTEGER
    DECLARE age : INTEGER
    REPEAT
        INPUT age
        IF age < 0 OR age > 120 THEN
            OUTPUT "Invalid age. Enter 0-120."
        ENDIF
    UNTIL age >= 0 AND age <= 120
    RETURN age
ENDFUNCTION

// Abnormal test data
Test 1: age = -10 → Expected: Error message, re-prompt
Test 2: age = 200 → Expected: Error message, re-prompt
Test 3: age = "abc" → Expected: Error or re-prompt
```

---

#### **3. Extreme/Boundary Data**

**Definition:**
Values at the edges of valid ranges, including minimum, maximum, and values just inside/outside boundaries.

**Also Called:**
- Boundary data
- Edge cases
- Limit values

**Purpose:**
- Test boundaries where errors often occur
- Verify range limits are correct
- Find off-by-one errors

**Boundary Testing Rules:**
For range MIN to MAX, test:
- MIN - 1 (just below, invalid)
- MIN (minimum valid)
- MIN + 1 (just above minimum)
- MAX - 1 (just below maximum)
- MAX (maximum valid)
- MAX + 1 (just above, invalid)

**Examples:**

**For age (0-120):**
- Boundary values:
  - -1 (invalid, just below)
  - 0 (valid, minimum)
  - 1 (valid, just above minimum)
  - 119 (valid, just below maximum)
  - 120 (valid, maximum)
  - 121 (invalid, just above)

**For percentage (0-100):**
- -1, 0, 1, 99, 100, 101

**For array index (0-9):**
- -1, 0, 1, 8, 9, 10

**For password length (8-20 characters):**
- 7 chars (invalid)
- 8 chars (valid, minimum)
- 9 chars (valid)
- 19 chars (valid)
- 20 chars (valid, maximum)
- 21 chars (invalid)

**Test Case Example:**

```pseudocode
// Function to test
FUNCTION IsValidPercentage(score : INTEGER) RETURNS BOOLEAN
    IF score >= 0 AND score <= 100 THEN
        RETURN TRUE
    ELSE
        RETURN FALSE
    ENDIF
ENDFUNCTION

// Boundary test data
Test 1: score = -1 → Expected: FALSE (just below)
Test 2: score = 0 → Expected: TRUE (minimum)
Test 3: score = 1 → Expected: TRUE (just above min)
Test 4: score = 50 → Expected: TRUE (middle - normal)
Test 5: score = 99 → Expected: TRUE (just below max)
Test 6: score = 100 → Expected: TRUE (maximum)
Test 7: score = 101 → Expected: FALSE (just above)
```

**Complete Testing Example:**

```pseudocode
FUNCTION CalculateGrade(score : INTEGER) RETURNS CHAR
    IF score < 0 OR score > 100 THEN
        RETURN 'X'  // Invalid
    ELSEIF score >= 70 THEN
        RETURN 'A'
    ELSEIF score >= 60 THEN
        RETURN 'B'
    ELSEIF score >= 50 THEN
        RETURN 'C'
    ELSEIF score >= 40 THEN
        RETURN 'D'
    ELSE
        RETURN 'F'
    ENDIF
ENDFUNCTION
```

**Test Plan:**

| Test ID | Type | Input | Expected | Purpose |
|---------|------|-------|----------|---------|
| T01 | Normal | 85 | 'A' | Typical high score |
| T02 | Normal | 65 | 'B' | Typical mid score |
| T03 | Normal | 35 | 'F' | Typical fail |
| T04 | Boundary | -1 | 'X' | Just below min |
| T05 | Boundary | 0 | 'F' | Minimum valid |
| T06 | Boundary | 1 | 'F' | Just above min |
| T07 | Boundary | 39 | 'F' | Just below D |
| T08 | Boundary | 40 | 'D' | Minimum D |
| T09 | Boundary | 41 | 'D' | Just above D |
| T10 | Boundary | 49 | 'D' | Just below C |
| T11 | Boundary | 50 | 'C' | Minimum C |
| T12 | Boundary | 59 | 'C' | Just below B |
| T13 | Boundary | 60 | 'B' | Minimum B |
| T14 | Boundary | 69 | 'B' | Just below A |
| T15 | Boundary | 70 | 'A' | Minimum A |
| T16 | Boundary | 99 | 'A' | Just below max |
| T17 | Boundary | 100 | 'A' | Maximum valid |
| T18 | Boundary | 101 | 'X' | Just above max |
| T19 | Abnormal | -50 | 'X' | Negative |
| T20 | Abnormal | 200 | 'X' | Way over max |

---

### **Program Maintenance**

#### **Need for Maintenance**

**Why Maintenance is Necessary:**
- Software is never perfect on release
- Requirements change over time
- Technology evolves
- Bugs discovered during use
- Performance improvements needed
- User needs change
- Legal/regulatory changes
- New features requested

**Maintenance Facts:**
- Maintenance is ongoing, not one-time
- Can cost more than initial development
- Requires good documentation
- May last years or decades
- Essential for system longevity

---

#### **Types of Maintenance**

### **1. Corrective Maintenance**

**Definition:**
Fixing errors and bugs discovered after the system is deployed.

**Purpose:**
- Fix defects
- Correct errors
- Resolve problems

**Examples:**
- Fix calculation error in payroll system
- Correct logic error causing wrong output
- Fix crash when invalid data entered
- Repair data corruption issue
- Fix security vulnerability

**Characteristics:**
- Reactive (responds to problems)
- Urgent (may need immediate fix)
- Can be costly if critical
- Preventable with better testing

**Example Scenario:**
"Users report that the library system calculates fines incorrectly. The fine should be $0.50 per day, but the system charges $5.00. The bug is in the calculation formula. Corrective maintenance: Change `fine ← days * 5.0` to `fine ← days * 0.5`"

---

### **2. Adaptive Maintenance**

**Definition:**
Modifying the system to work in a changed or changing environment.

**Purpose:**
- Adapt to new environment
- Work with new platforms
- Comply with new standards
- Support new hardware/software

**Examples:**
- Update software for new operating system (Windows 10 → Windows 11)
- Modify to work with new database version
- Adapt for new hardware (printer, scanner)
- Update for new web browser versions
- Change date format for different country
- Modify for new payment gateway API
- Update for GDPR compliance

**Characteristics:**
- Often mandatory (environment forces change)
- Planned in advance
- May affect whole system
- Regular occurrence

**Example Scenario:**
"The school system was built for Windows 7. Microsoft ends Windows 7 support. Adaptive maintenance: Update the software to be compatible with Windows 10, modify file access methods, update UI for new OS features."

---

### **3. Perfective Maintenance**

**Definition:**
Enhancing the system by adding new features or improving existing functionality based on user requests.

**Purpose:**
- Add new features
- Improve performance
- Enhance user experience
- Increase efficiency
- Add functionality

**Examples:**
- Add email notification feature to library system
- Improve search speed by optimizing algorithm
- Add dark mode to user interface
- Add export to Excel feature
- Improve report formatting
- Add data visualization dashboard
- Optimize database queries for faster response
- Add mobile app version
- Improve user interface design

**Characteristics:**
- Proactive improvement
- Adds value
- User-driven
- Optional (not fixing errors)
- Continuous process

**Example Scenario:**
"Users request the ability to search books by multiple criteria (author AND title AND year). Currently, only single-criteria search exists. Perfective maintenance: Add advanced search feature allowing combined search criteria with AND/OR operators."

---

**Comparison of Maintenance Types:**

| Type | Why? | When? | Example |
|------|------|-------|---------|
| Corrective | Fix bugs | After error found | Fix calculation error |
| Adaptive | Environment changed | New platform/tech | Update for new OS |
| Perfective | Improve system | User requests | Add new feature |

**Maintenance Example Program:**

```pseudocode
// Original Version 1.0
FUNCTION CalculateFine(daysLate : INTEGER) RETURNS REAL
    RETURN daysLate * 5.0  // BUG: Should be 0.5
ENDFUNCTION

// After CORRECTIVE maintenance (Version 1.1)
FUNCTION CalculateFine(daysLate : INTEGER) RETURNS REAL
    RETURN daysLate * 0.5  // FIXED: Correct rate
ENDFUNCTION

// After ADAPTIVE maintenance (Version 2.0)
// Adapted for new currency system
FUNCTION CalculateFine(daysLate : INTEGER, currency : STRING) 
    RETURNS REAL
    DECLARE rate : REAL
    
    CASE OF currency
        "USD": rate ← 0.5
        "EUR": rate ← 0.45
        "GBP": rate ← 0.40
    ENDCASE
    
    RETURN daysLate * rate
ENDFUNCTION

// After PERFECTIVE maintenance (Version 3.0)
// Added grace period and maximum fine features
FUNCTION CalculateFine(daysLate : INTEGER, currency : STRING,
                       gracePeriod : INTEGER, maxFine : REAL) 
    RETURNS REAL
    DECLARE rate : REAL
    DECLARE fine : REAL
    
    // New feature: Grace period
    IF daysLate <= gracePeriod THEN
        RETURN 0
    ENDIF
    
    daysLate ← daysLate - gracePeriod
    
    CASE OF currency
        "USD": rate ← 0.5
        "EUR": rate ← 0.45
        "GBP": rate ← 0.40
    ENDCASE
    
    fine ← daysLate * rate
    
    // New feature: Maximum fine cap
    IF fine > maxFine THEN
        fine ← maxFine
    ENDIF
    
    RETURN fine
ENDFUNCTION
```

---

### **Analysing and Amending Existing Programs**

**Process for Analysing Existing Code:**

1. **Read and Understand**
   - Read through entire code
   - Identify main components
   - Understand program flow
   - Note any documentation

2. **Identify Structure**
   - Find main program
   - Locate procedures/functions
   - Identify data structures
   - Map module interactions

3. **Trace Logic**
   - Follow execution path
   - Understand algorithms
   - Note decision points
   - Identify loops

4. **Locate Issues**
   - Find areas needing change
   - Identify potential problems
   - Note inefficiencies
   - Check for errors

5. **Plan Amendments**
   - Decide what to change
   - Consider impact on other parts
   - Plan testing strategy
   - Document changes

**Example: Enhancing a Program**

**Original Program:**

```pseudocode
// Simple calculator - Version 1.0
DECLARE num1, num2 : INTEGER
DECLARE result : INTEGER
DECLARE operation : CHAR

INPUT num1
INPUT num2
INPUT operation

IF operation = '+' THEN
    result ← num1 + num2
ENDIF

IF operation = '-' THEN
    result ← num1 - num2
ENDIF

OUTPUT result
```

**Analysis:**
- Only handles addition and subtraction
- No error handling
- Limited to integers
- No validation
- Needs enhancement

**Enhanced Version:**

```pseudocode
// Enhanced calculator - Version 2.0
DECLARE num1, num2 : REAL  // Changed to REAL
DECLARE result : REAL
DECLARE operation : CHAR
DECLARE isValid : BOOLEAN

// Input validation
REPEAT
    OUTPUT "Enter first number: "
    INPUT num1
    OUTPUT "Enter second number: "
    INPUT num2
    OUTPUT "Enter operation (+, -, *, /): "
    INPUT operation
    
    isValid ← TRUE
    
    // Validate operation
    IF operation <> '+' AND operation <> '-' AND 
       operation <> '*' AND operation <> '/' THEN
        OUTPUT "Invalid operation"
        isValid ← FALSE
    ENDIF
    
    // Check division by zero
    IF operation = '/' AND num2 = 0 THEN
        OUTPUT "Cannot divide by zero"
        isValid ← FALSE
    ENDIF
UNTIL isValid

// Perform calculation using CASE
CASE OF operation
    '+': result ← num1 + num2
    '-': result ← num1 - num2
    '*': result ← num1 * num2
    '/': result ← num1 / num2
ENDCASE

OUTPUT num1, " ", operation, " ", num2, " = ", result
```

**Amendments Made:**
1. Changed INTEGER to REAL (adaptive/perfective)
2. Added multiplication and division (perfective)
3. Added input validation (perfective)
4. Added division by zero check (corrective/perfective)
5. Replaced multiple IFs with CASE (perfective)
6. Improved output format (perfective)

---

## Summary of Key Concepts

### **Algorithm Design**
- Abstraction: Simplify by removing unnecessary details
- Decomposition: Break problems into sub-problems
- Use appropriate constructs: sequence, selection, iteration
- Document with flowcharts, pseudocode, structured English

### **Data Structures**
- Choose appropriate data types for the task
- Use records to group related data
- Use arrays for collections of similar data
- Understand ADTs: stacks (LIFO), queues (FIFO), linked lists

### **Programming**
- Use procedures for actions, functions for calculations
- Pass parameters by value or by reference
- Write efficient, modular code
- Use meaningful identifiers

### **Development Life Cycles**
- Waterfall: Sequential, good for stable requirements
- Iterative: Repeated cycles, flexible
- RAD: Fast development with prototypes

### **Testing**
- Test with normal, abnormal, and boundary data
- Use multiple testing methods: dry run, white-box, black-box
- Create comprehensive test plans
- Test throughout development

### **Maintenance**
- Corrective: Fix bugs
- Adaptive: Adapt to environment
- Perfective: Add features/improvements
- All systems require ongoing maintenance

---

## Practice Questions

**Question 1:** Write pseudocode to input 10 numbers into an array, find the average, and count how many are above average.

**Question 2:** Draw a structure chart for a program that manages a shop's inventory (add items, remove items, search items, display all items).

**Question 3:** Create a test plan with normal, abnormal, and boundary data for a function that validates exam scores (0-100).

**Question 4:** Explain the difference between a stack and a queue, giving a real-world example of each.

**Question 5:** A library system currently only tracks books. Describe what type of maintenance would be needed to: (a) fix a bug in the date calculation, (b) add DVD tracking, (c) make it work on a new database system.

---

*End of Complete Theory Notes*
*Cambridge International AS & A Level Computer Science 9618*
*Sections 9-12: Algorithm Design, Data Structures, Programming, and Software Development*
