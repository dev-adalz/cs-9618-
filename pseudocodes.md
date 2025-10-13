# Cambridge A Level Computer Science 9618 - Complete Pseudocode Guide

## Introduction

This guide provides comprehensive rules and conventions for writing pseudocode according to Cambridge International AS & A Level Computer Science 9618 standards (for exams from 2026).

---

## 1. Pseudocode Formatting Rules

### 1.1 Font Style and Size
- Pseudocode uses **monospaced (fixed-width) font** like Courier New
- Font size is consistent throughout
- This makes code align properly and improves readability

### 1.2 Indentation
- Lines are indented (usually **3 spaces**) to show they're inside a control structure
- Indentation shows which statements belong to which block
- When line numbering is used, indentation may be omitted
- Continuation lines are aligned for maximum readability

**Example:**
```pseudocode
IF score > 50 THEN
   OUTPUT "Pass"        // indented 3 spaces
   total ← total + 1    // indented 3 spaces
ENDIF
```

### 1.3 Case Conventions

**KEYWORDS:** Always in UPPER-CASE
- Examples: `IF`, `THEN`, `REPEAT`, `PROCEDURE`, `FUNCTION`, `DECLARE`

**Identifiers:** Mixed case (camelCase or PascalCase)
- Examples: `studentName`, `TotalScore`, `numberOfPlayers`
- First letter of new words is capitalized
- Makes identifiers readable

**Meta-variables:** Enclosed in angle brackets `< >`
- Used to show what should be substituted
- Examples: `<identifier>`, `<condition>`, `<statement(s)>`

**Example:**
```pseudocode
// Keywords in UPPER-CASE, identifiers in camelCase
DECLARE totalScore : INTEGER
IF totalScore > 100 THEN
   OUTPUT "High score!"
ENDIF
```

### 1.4 Line Numbering
- Line numbers appear to the **left** of code with sufficient spacing
- Numbers are **consecutive** unless skipped to show missing code
- Each statement gets one number
- Continuation lines are **not numbered**

**Example:**
```pseudocode
01  DECLARE total : INTEGER
02  total ← 0
03  FOR i ← 1 TO 10
04     total ← total + i
05  NEXT i
```

### 1.5 Comments
- Comments start with **two forward slashes** `//`
- Comment continues until end of line
- Multi-line comments: each line starts with `//`
- Usually on separate line **before** the code, at same indentation level
- Short comments may appear at **end of line**

**Example:**
```pseudocode
// This procedure calculates
// the total of all scores
PROCEDURE CalculateTotal()
   total ← 0
   counter ← 1  // initialize counter
   WHILE counter <= 10
      total ← total + score[counter]
      counter ← counter + 1
   ENDWHILE
ENDPROCEDURE
```

---

## 2. Variables, Constants and Data Types

### 2.1 Data Types

Cambridge 9618 uses these standard data types:

| Data Type | Description | Example Values |
|-----------|-------------|----------------|
| `INTEGER` | Whole number | 5, -3, 0, 1000 |
| `REAL` | Number with fractional part | 4.7, 0.3, -4.0, 0.0 |
| `CHAR` | Single character | 'x', 'C', '@' |
| `STRING` | Sequence of characters | "Hello", "Computer Science", "" |
| `BOOLEAN` | Logical value | TRUE, FALSE |
| `DATE` | Calendar date | 15/03/2024, 01/01/2025 |

### 2.2 Literals

**How to write literal values:**

**INTEGER:**
```pseudocode
5
-3
0
1000
```

**REAL:**
- Always written with **at least one digit on either side** of decimal point
- Add zeros if necessary
```pseudocode
4.7       // correct
0.3       // correct
-4.0      // correct (not -4)
0.0       // correct (not 0)
```

**CHAR:**
- Single character in **single quotes** `' '`
```pseudocode
'x'
'C'
'@'
'5'
```

**STRING:**
- Text in **double quotes** `" "`
- Can be empty string `""`
```pseudocode
"This is a string"
"Hello World"
""              // empty string
"123"           // string, not number
```

**BOOLEAN:**
```pseudocode
TRUE
FALSE
```

**DATE:**
- Format: `dd/mm/yyyy`
- Should explicitly state it's DATE type
```pseudocode
15/03/2024
01/01/2025
```

### 2.3 Identifiers (Naming Rules)

**Rules for naming variables, constants, procedures, functions:**

1. **Can contain:**
   - Letters (A-Z, a-z)
   - Digits (0-9)
   - Underscore `_`

2. **Must start with a letter** (not a digit)

3. **Cannot use keywords** (IF, THEN, FOR, etc.)

4. **Use mixed case** (camelCase or PascalCase)

5. **Case insensitive** - `CountDown` and `Countdown` are considered the same

6. **Be descriptive and meaningful**

**Good Examples:**
```pseudocode
studentName        // descriptive
totalScore         // clear meaning
numberOfAttempts   // explains purpose
isValid           // Boolean flag (is...)
maxValue          // maximum value
```

**Acceptable Single Letters:**
```pseudocode
i, j, k           // loop counters
x, y              // coordinates
n                 // count/number
```

**Bad Examples:**
```pseudocode
x1                // not descriptive (except coordinates)
temp              // too vague (what temp?)
a, b, c           // meaningless (except in specific math contexts)
2ndScore          // starts with digit (INVALID)
student-name      // contains hyphen (INVALID)
```

### 2.4 Variable Declarations

**Syntax:**
```pseudocode
DECLARE <identifier> : <data type>
```

**Examples:**
```pseudocode
// Single declarations
DECLARE counter : INTEGER
DECLARE totalToPay : REAL
DECLARE studentName : STRING
DECLARE isValid : BOOLEAN
DECLARE birthDate : DATE
DECLARE grade : CHAR

// Multiple declarations of same type
DECLARE x, y, z : INTEGER
DECLARE firstName, lastName : STRING
```

**Best Practice:**
- Declare all variables at the start of your program/procedure
- Group related variables together
- Add comments to explain complex variables

### 2.5 Constants

**Purpose:**
- Values that never change during program execution
- Make code more readable
- Easier to update (change in one place)
- More meaningful than "magic numbers"

**Syntax:**
```pseudocode
CONSTANT <identifier> = <value>
```

**Important Rules:**
- Only **literals** can be used as values
- Cannot use variables, expressions, or other constants
- Declared at **beginning** of pseudocode
- By convention, may use ALL_CAPS or camelCase

**Examples:**
```pseudocode
CONSTANT Pi = 3.14159
CONSTANT HourlyRate = 6.50
CONSTANT MaxStudents = 30
CONSTANT DefaultText = "N/A"
CONSTANT TaxRate = 0.15
CONSTANT SchoolName = "Cambridge International"
```

**Using Constants:**
```pseudocode
CONSTANT Pi = 3.14159
CONSTANT MaxScore = 100

DECLARE radius : REAL
DECLARE circumference : REAL
DECLARE score : INTEGER

INPUT radius
circumference ← 2 * Pi * radius

IF score > MaxScore THEN
   OUTPUT "Invalid score"
ENDIF
```

### 2.6 Assignments

**Syntax:**
```pseudocode
<identifier> ← <value>
```

**The assignment operator is** `←` (left arrow)

**Rules:**
- Identifier must be a variable (or array element, record field)
- Value can be any expression that evaluates to correct data type
- Value is calculated FIRST, then stored in variable

**Examples:**
```pseudocode
// Simple assignments
counter ← 0
price ← 19.99
name ← "Alice"
isValid ← TRUE

// Assignment with expressions
counter ← counter + 1
total ← price * quantity
average ← sum / count
fullName ← firstName & " " & lastName

// Assignment with function result
length ← LENGTH(name)
maximum ← Max(a, b)
```

---

## 3. Arrays

### 3.1 Declaring Arrays

**One-Dimensional Array:**
```pseudocode
DECLARE <identifier> : ARRAY[<lower>:<upper>] OF <data type>
```

**Two-Dimensional Array:**
```pseudocode
DECLARE <identifier> : ARRAY[<lower1>:<upper1>, <lower2>:<upper2>] OF <data type>
```

**Key Points:**
- Arrays have **fixed length**
- All elements are **same data type**
- Use **square brackets** `[ ]`
- Lower bound is usually **1** (but can be 0)
- Upper bound defines last index
- Good practice to explicitly state lower bound

**Examples:**
```pseudocode
// 1D arrays (30 elements, indices 1 to 30)
DECLARE studentNames : ARRAY[1:30] OF STRING
DECLARE scores : ARRAY[1:30] OF INTEGER
DECLARE prices : ARRAY[1:100] OF REAL

// 1D array starting from 0
DECLARE temperatures : ARRAY[0:6] OF REAL  // 7 elements (0-6)

// 2D arrays
DECLARE grid : ARRAY[1:10, 1:10] OF INTEGER  // 10x10 grid
DECLARE classroom : ARRAY[1:5, 1:6] OF STRING  // 5 rows, 6 columns
DECLARE noughtsAndCrosses : ARRAY[1:3, 1:3] OF CHAR  // 3x3 grid
```

### 3.2 Using Arrays

**Accessing Individual Elements:**

**1D Array:**
```pseudocode
DECLARE scores : ARRAY[1:5] OF INTEGER

// Assign values
scores[1] ← 85
scores[2] ← 92
scores[3] ← 78
scores[n] ← 95
scores[i+1] ← scores[i]

// Read values
OUTPUT scores[1]
total ← total + scores[3]
```

**2D Array:**
```pseudocode
DECLARE grid : ARRAY[1:3, 1:3] OF INTEGER

// Assign values
grid[1, 1] ← 10
grid[2, 3] ← 25
grid[row, col] ← 0

// Read values
OUTPUT grid[1, 2]
sum ← sum + grid[i, j]
```

**Assigning Complete Arrays:**
```pseudocode
DECLARE gameBoard : ARRAY[1:3, 1:3] OF CHAR
DECLARE savedGame : ARRAY[1:3, 1:3] OF CHAR

// Copy entire array (must be same size and type)
savedGame ← gameBoard
```

**IMPORTANT - Cannot Assign Groups:**
```pseudocode
// This is WRONG - do not do this
studentNames[1 TO 30] ← ""  // INVALID

// Instead, use a loop
FOR i ← 1 TO 30
   studentNames[i] ← ""
NEXT i
```

**Common Array Operations:**

**Fill Array:**
```pseudocode
DECLARE numbers : ARRAY[1:10] OF INTEGER

// Fill with zeros
FOR i ← 1 TO 10
   numbers[i] ← 0
NEXT i

// Fill with input
FOR i ← 1 TO 10
   OUTPUT "Enter number ", i
   INPUT numbers[i]
NEXT i
```

**Display Array:**
```pseudocode
// Display all elements
FOR i ← 1 TO 10
   OUTPUT numbers[i]
NEXT i

// Display with formatting
FOR i ← 1 TO 10
   OUTPUT "Element ", i, ": ", numbers[i]
NEXT i
```

**2D Array Operations:**
```pseudocode
DECLARE grid : ARRAY[1:3, 1:4] OF INTEGER

// Fill 2D array
FOR row ← 1 TO 3
   FOR col ← 1 TO 4
      INPUT grid[row, col]
   NEXT col
NEXT row

// Display 2D array
FOR row ← 1 TO 3
   FOR col ← 1 TO 4
      OUTPUT grid[row, col], " "
   NEXT col
   OUTPUT ""  // new line after each row
NEXT row

// Sum all elements
total ← 0
FOR row ← 1 TO 3
   FOR col ← 1 TO 4
      total ← total + grid[row, col]
   NEXT col
NEXT row
```

---

## 4. User-Defined Data Types

### 4.1 Non-Composite Types

#### **Enumerated Type**

An enumerated type has a list of specific possible values.

**Syntax:**
```pseudocode
TYPE <identifier> = (value1, value2, value3, ...)
```

**Examples:**
```pseudocode
TYPE Season = (Spring, Summer, Autumn, Winter)
TYPE DayOfWeek = (Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday)
TYPE Grade = (A, B, C, D, E, F)
TYPE Status = (Active, Inactive, Pending, Cancelled)
```

**Using Enumerated Types:**
```pseudocode
DECLARE currentSeason : Season
DECLARE today : DayOfWeek

currentSeason ← Summer
today ← Monday

IF currentSeason = Winter THEN
   OUTPUT "It's cold!"
ENDIF
```

#### **Pointer Type**

A pointer references a memory location.

**Syntax:**
```pseudocode
TYPE <identifier> = ^<data type>
```

**The ^ symbol indicates a pointer**

**Examples:**
```pseudocode
TYPE TIntPointer = ^INTEGER
TYPE TCharPointer = ^CHAR
TYPE TRealPointer = ^REAL
```

**Declaring and Using Pointers:**
```pseudocode
// Declare pointer type
TYPE TIntPointer = ^INTEGER

// Declare pointer variable (no ^ needed here)
DECLARE myPointer : TIntPointer
DECLARE value : INTEGER

value ← 100

// Assign address
myPointer ← ^value

// Access value at address (dereference)
OUTPUT myPointer^  // outputs 100
```

### 4.2 Composite Types

#### **Record Type**

A record groups different data types under one identifier.

**Syntax:**
```pseudocode
TYPE <identifier1>
   DECLARE <identifier2> : <data type>
   DECLARE <identifier3> : <data type>
   ...
ENDTYPE
```

**Examples:**
```pseudocode
// Student record
TYPE StudentRecord
   DECLARE lastName : STRING
   DECLARE firstName : STRING
   DECLARE dateOfBirth : DATE
   DECLARE yearGroup : INTEGER
   DECLARE formGroup : CHAR
ENDTYPE

// Book record
TYPE Book
   DECLARE isbn : STRING
   DECLARE title : STRING
   DECLARE author : STRING
   DECLARE price : REAL
   DECLARE inStock : BOOLEAN
ENDTYPE

// Product record
TYPE Product
   DECLARE productID : INTEGER
   DECLARE productName : STRING
   DECLARE quantity : INTEGER
   DECLARE price : REAL
ENDTYPE
```

**Using Records:**
```pseudocode
// Declare variables of record type
DECLARE pupil1 : StudentRecord
DECLARE pupil2 : StudentRecord
DECLARE class : ARRAY[1:30] OF StudentRecord

// Assign values using dot notation
pupil1.lastName ← "Johnson"
pupil1.firstName ← "Leroy"
pupil1.dateOfBirth ← 02/01/2005
pupil1.yearGroup ← 6
pupil1.formGroup ← 'A'

// Copy entire record
pupil2 ← pupil1

// Access values
OUTPUT pupil1.firstName, " ", pupil1.lastName
IF pupil1.yearGroup = 6 THEN
   OUTPUT "Sixth form student"
ENDIF

// Array of records
FOR i ← 1 TO 30
   class[i].yearGroup ← class[i].yearGroup + 1
NEXT i
```

#### **Set Type**

A set is a collection of unique values.

**Syntax:**
```pseudocode
TYPE <identifier1> = SET OF <data type>
DEFINE <identifier2> (value1, value2, value3, ...) : <identifier1>
```

**Example:**
```pseudocode
// Define set type
TYPE LetterSet = SET OF CHAR

// Define specific set
DEFINE Vowels ('A', 'E', 'I', 'O', 'U') : LetterSet
DEFINE Digits ('0', '1', '2', '3', '4', '5', '6', '7', '8', '9') : LetterSet
```

---

## 5. Common Operations

### 5.1 Input and Output

#### **INPUT Statement**

**Syntax:**
```pseudocode
INPUT <identifier>
```

- Identifier must be a variable
- Can be array element or record field
- Waits for user to enter value

**Examples:**
```pseudocode
DECLARE age : INTEGER
DECLARE name : STRING
DECLARE scores : ARRAY[1:5] OF INTEGER

// Simple input
INPUT age
INPUT name

// Array element input
INPUT scores[1]
INPUT scores[i]

// Record field input
INPUT pupil.firstName

// Input with prompt (best practice)
OUTPUT "Enter your name: "
INPUT name

OUTPUT "Enter your age: "
INPUT age
```

#### **OUTPUT Statement**

**Syntax:**
```pseudocode
OUTPUT <value(s)>
```

- Can output multiple values separated by commas
- Values can be literals, variables, or expressions

**Examples:**
```pseudocode
// Simple output
OUTPUT "Hello World"
OUTPUT age
OUTPUT scores[1]

// Multiple values
OUTPUT "Name: ", name
OUTPUT "Age: ", age
OUTPUT "You have ", lives, " lives left"

// Expressions
OUTPUT "Total: ", price * quantity
OUTPUT firstName, " ", lastName
OUTPUT "Average: ", total / count
```

### 5.2 Arithmetic Operations

| Operator | Operation | Example | Result |
|----------|-----------|---------|--------|
| `+` | Addition | `5 + 3` | `8` |
| `-` | Subtraction | `10 - 4` | `6` |
| `*` | Multiplication | `6 * 7` | `42` |
| `/` | Division (real) | `15 / 2` | `7.5` |
| `DIV` | Integer division | `15 DIV 2` | `7` |
| `MOD` | Modulus (remainder) | `15 MOD 2` | `1` |

**Important Notes:**
- `/` always produces REAL result (even with integers)
- `DIV` produces INTEGER result (quotient only)
- `MOD` produces remainder after division
- Multiplication and division have **higher precedence** than addition/subtraction
- Use **parentheses** to make order explicit

**Examples:**
```pseudocode
DECLARE a, b, result : INTEGER
DECLARE total : REAL

a ← 15
b ← 2

result ← a + b        // result = 17
result ← a - b        // result = 13
result ← a * b        // result = 30
total ← a / b         // total = 7.5
result ← a DIV b      // result = 7
result ← a MOD b      // result = 1

// Precedence examples
result ← 2 + 3 * 4    // result = 14 (not 20)
result ← (2 + 3) * 4  // result = 20

// Modulus examples
result ← 10 MOD 3     // result = 1
result ← 17 MOD 5     // result = 2
result ← 20 MOD 4     // result = 0

// Check if even
IF number MOD 2 = 0 THEN
   OUTPUT "Even"
ENDIF
```

### 5.3 Relational Operations (Comparison)

| Operator | Meaning | Example |
|----------|---------|---------|
| `>` | Greater than | `score > 50` |
| `<` | Less than | `age < 18` |
| `>=` | Greater than or equal | `score >= 50` |
| `<=` | Less than or equal | `age <= 65` |
| `=` | Equal to | `answer = "Yes"` |
| `<>` | Not equal to | `status <> "Complete"` |

**Result:** Always produces BOOLEAN (TRUE or FALSE)

**Examples:**
```pseudocode
DECLARE age, score : INTEGER
DECLARE result : BOOLEAN

age ← 17
score ← 85

result ← age > 18         // FALSE
result ← age < 18         // TRUE
result ← score >= 50      // TRUE
result ← score <= 100     // TRUE
result ← age = 17         // TRUE
result ← score <> 85      // FALSE

// In conditions
IF age >= 18 THEN
   OUTPUT "Adult"
ENDIF

IF score < 50 THEN
   OUTPUT "Fail"
ENDIF
```

### 5.4 Logic Operators

| Operator | Meaning | Example |
|----------|---------|---------|
| `AND` | Both must be true | `age >= 18 AND hasLicense = TRUE` |
| `OR` | At least one must be true | `grade = 'A' OR grade = 'B'` |
| `NOT` | Reverses truth value | `NOT isComplete` |

**Operands and results are always BOOLEAN**

**Truth Tables:**

**AND:**
| A | B | A AND B |
|---|---|---------|
| TRUE | TRUE | TRUE |
| TRUE | FALSE | FALSE |
| FALSE | TRUE | FALSE |
| FALSE | FALSE | FALSE |

**OR:**
| A | B | A OR B |
|---|---|--------|
| TRUE | TRUE | TRUE |
| TRUE | FALSE | TRUE |
| FALSE | TRUE | TRUE |
| FALSE | FALSE | FALSE |

**NOT:**
| A | NOT A |
|---|-------|
| TRUE | FALSE |
| FALSE | TRUE |

**Examples:**
```pseudocode
// AND - both conditions must be true
IF age >= 18 AND hasLicense = TRUE THEN
   OUTPUT "Can drive"
ENDIF

IF score >= 50 AND attendance >= 75 THEN
   OUTPUT "Eligible for exam"
ENDIF

// OR - at least one condition must be true
IF day = "Saturday" OR day = "Sunday" THEN
   OUTPUT "Weekend"
ENDIF

IF grade = 'A' OR grade = 'B' OR grade = 'C' THEN
   OUTPUT "Good grade"
ENDIF

// NOT - reverses condition
IF NOT isComplete THEN
   OUTPUT "Still in progress"
ENDIF

IF NOT (age < 18) THEN
   OUTPUT "Adult"
ENDIF

// Complex expressions - use parentheses
IF (score >= 40 AND attendance >= 75) OR hasExemption = TRUE THEN
   OUTPUT "Can take exam"
ENDIF

IF NOT (status = "Complete" OR status = "Cancelled") THEN
   OUTPUT "Still active"
ENDIF
```

### 5.5 String Functions and Operations

**IMPORTANT:** String functions will always be provided in examinations.

#### **String Functions**

**LENGTH(ThisString : STRING) RETURNS INTEGER**
- Returns length of string
```pseudocode
len ← LENGTH("Hello")  // len = 5
len ← LENGTH("Computer Science")  // len = 16
len ← LENGTH("")  // len = 0
```

**RIGHT(ThisString : STRING, x : INTEGER) RETURNS STRING**
- Returns rightmost x characters
```pseudocode
result ← RIGHT("ABCDEFGH", 3)  // result = "FGH"
result ← RIGHT("Hello", 2)  // result = "lo"
```

**MID(ThisString : STRING, x : INTEGER, y : INTEGER) RETURNS STRING**
- Returns substring of length y starting at position x
- Position counting starts at 1
```pseudocode
result ← MID("ABCDEFGH", 2, 3)  // result = "BCD"
result ← MID("Computer", 1, 4)  // result = "Comp"
result ← MID("Hello World", 7, 5)  // result = "World"
```

**LCASE(ThisChar : CHAR) RETURNS CHAR**
- Converts character to lowercase
- If not uppercase letter, returns unchanged
```pseudocode
result ← LCASE('W')  // result = 'w'
result ← LCASE('A')  // result = 'a'
result ← LCASE('5')  // result = '5' (unchanged)
```

**UCASE(ThisChar : CHAR) RETURNS CHAR**
- Converts character to uppercase
- If not lowercase letter, returns unchanged
```pseudocode
result ← UCASE('h')  // result = 'H'
result ← UCASE('w')  // result = 'W'
result ← UCASE('9')  // result = '9' (unchanged)
```

#### **String Concatenation**

**Operator:** `&`

```pseudocode
// Joining strings
fullName ← "John" & " " & "Smith"  // fullName = "John Smith"
greeting ← "Hello " & name  // e.g., "Hello Alice"
message ← "You have " & "5" & " lives"  // "You have 5 lives"

// Example
firstName ← "Summer"
lastName ← "Pudding"
fullName ← firstName & " " & lastName  // "Summer Pudding"
```

**Complete String Example:**
```pseudocode
DECLARE name : STRING
DECLARE initial : CHAR
DECLARE nameLength : INTEGER

INPUT name
nameLength ← LENGTH(name)

OUTPUT "Name: ", name
OUTPUT "Length: ", nameLength

initial ← UCASE(MID(name, 1, 1))
OUTPUT "Initial: ", initial

lastThree ← RIGHT(name, 3)
OUTPUT "Last 3 letters: ", lastThree
```

### 5.6 Numeric Functions

**INT(x : REAL) RETURNS INTEGER**
- Returns integer part of number (truncates decimal)
- Does NOT round

```pseudocode
result ← INT(27.5415)  // result = 27
result ← INT(9.99)     // result = 9
result ← INT(3.14)     // result = 3
result ← INT(-5.7)     // result = -5
```

**RAND(x : INTEGER) RETURNS REAL**
- Returns random real number
- Range: 0 to x (not including x)
- Different value each time

```pseudocode
random ← RAND(10)  // e.g., 7.823 (0 <= result < 10)
random ← RAND(100)  // e.g., 45.67 (0 <= result < 100)

// Random integer from 1 to 6 (dice)
dice ← INT(RAND(6)) + 1

// Random integer from 1 to 10
number ← INT(RAND(10)) + 1

// Random integer from 0 to 9
number ← INT(RAND(10))
```

---

## 6. Selection

### 6.1 IF Statements

#### **Simple IF (without ELSE)**

**Syntax:**
```pseudocode
IF <condition> THEN
   <statement(s)>
ENDIF
```

**Examples:**
```pseudocode
IF age >= 18 THEN
   OUTPUT "Adult"
ENDIF

IF score > 100 THEN
   OUTPUT "Invalid score"
   score ← 100
ENDIF

IF temperature < 0 THEN
   OUTPUT "Freezing"
ENDIF
```

#### **IF with ELSE**

**Syntax:**
```pseudocode
IF <condition> THEN
   <statement(s)>
ELSE
   <statement(s)>
ENDIF
```

**Examples:**
```pseudocode
IF age >= 18 THEN
   OUTPUT "Adult"
ELSE
   OUTPUT "Minor"
ENDIF

IF score >= 50 THEN
   OUTPUT "Pass"
ELSE
   OUTPUT "Fail"
ENDIF
```

#### **IF-ELSEIF-ELSE (Multiple Conditions)**

**Syntax:**
```pseudocode
IF <condition1> THEN
   <statement(s)>
ELSEIF <condition2> THEN
   <statement(s)>
ELSEIF <condition3> THEN
   <statement(s)>
ELSE
   <statement(s)>
ENDIF
```

**Examples:**
```pseudocode
// Grade calculator
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

// Temperature classification
IF temperature < 0 THEN
   OUTPUT "Freezing"
ELSEIF temperature < 15 THEN
   OUTPUT "Cold"
ELSEIF temperature < 25 THEN
   OUTPUT "Moderate"
ELSE
   OUTPUT "Hot"
ENDIF
```

#### **Nested IF Statements**

**IF inside another IF:**

```pseudocode
IF challengerScore > championScore THEN
   IF challengerScore > highestScore THEN
      OUTPUT challengerName, " is champion and highest scorer"
   ELSE
      OUTPUT challengerName, " is the new champion"
   ENDIF
ELSE
   OUTPUT championName, " is still the champion"
   IF championScore > highestScore THEN
      OUTPUT championName, " is also the highest scorer"
   ENDIF
ENDIF
```

**Note:** THEN and ELSE may be indented by 2 spaces instead of 3 due to space constraints.

### 6.2 CASE Statements

**Purpose:**
- Better alternative to multiple IF-ELSEIF when checking **one variable** against many values
- Cleaner and more readable

**Basic Syntax:**
```pseudocode
CASE OF <identifier>
   <value1> : <statement(s)>
   <value2> : <statement(s)>
   <value3> : <statement(s)>
   ...
ENDCASE
```

**With OTHERWISE (default case):**
```pseudocode
CASE OF <identifier>
   <value1> : <statement(s)>
   <value2> : <statement(s)>
   <value3> : <statement(s)>
   OTHERWISE : <statement(s)>
ENDCASE
```

**Important Rules:**
- Cases tested in sequence from top to bottom
- When a matching case is found, its statements execute
- Control passes to statement after ENDCASE
- Remaining cases are NOT tested
- OTHERWISE is optional but should be last

**Examples:**
```pseudocode
// Menu selection
CASE OF choice
   1 : OUTPUT "New Game"
       CALL StartGame()
   2 : OUTPUT "Load Game"
       CALL LoadGame()
   3 : OUTPUT "Settings"
       CALL ShowSettings()
   4 : OUTPUT "Exit"
   OTHERWISE : OUTPUT "Invalid choice"
ENDCASE

// Grade to description
CASE OF grade
   'A' : OUTPUT "Excellent"
   'B' : OUTPUT "Good"
   'C' : OUTPUT "Satisfactory"
   'D' : OUTPUT "Pass"
   'F' : OUTPUT "Fail"
   OTHERWISE : OUTPUT "Invalid grade"
ENDCASE

// Day of week
CASE OF day
   1 : dayName ← "Monday"
   2 : dayName ← "Tuesday"
   3 : dayName ← "Wednesday"
   4 : dayName ← "Thursday"
   5 : dayName ← "Friday"
   6 : dayName ← "Saturday"
   7 : dayName ← "Sunday"
   OTHERWISE : dayName ← "Invalid day"
ENDCASE

// Move character in game
INPUT move
CASE OF move
   'W' : position ← position - 10
   'S' : position ← position + 10
   'A' : position ← position - 1
   'D' : position ← position + 1
   OTHERWISE : CALL Beep()
ENDCASE
```

**Range Values:**
```pseudocode
// Using ranges (value1 TO value2)
CASE OF score
   90 TO 100 : grade ← 'A'
   80 TO 89  : grade ← 'B'
   70 TO 79  : grade ← 'C'
   60 TO 69  : grade ← 'D'
   0 TO 59   : grade ← 'F'
   OTHERWISE : OUTPUT "Invalid score"
ENDCASE
```

---

## 7. Iteration (Repetition/Loops)

### 7.1 Count-Controlled (FOR) Loops

**Purpose:** When you know how many times to repeat

**Basic Syntax:**
```pseudocode
FOR <identifier> ← <value1> TO <value2>
   <statement(s)>
NEXT <identifier>
```

**Rules:**
- Identifier must be INTEGER variable
- value1 and value2 must evaluate to integers
- Variable assigned each value from value1 to value2 inclusive
- If value1 = value2, executes once
- If value1 > value2, doesn't execute
- Good practice to repeat identifier after NEXT

**Examples:**
```pseudocode
// Count 1 to 10
FOR i ← 1 TO 10
   OUTPUT i
NEXT i

// Process array
FOR index ← 1 TO 30
   OUTPUT studentNames[index]
NEXT index

// Calculate sum
total ← 0
FOR counter ← 1 TO 100
   total ← total + counter
NEXT counter

// Times table
FOR i ← 1 TO 12
   OUTPUT i, " x 7 = ", i * 7
NEXT i
```

**FOR Loop with STEP:**

**Syntax:**
```pseudocode
FOR <identifier> ← <value1> TO <value2> STEP <increment>
   <statement(s)>
NEXT <identifier>
```

**Rules:**
- Increment must evaluate to an integer
- Can be positive or negative
- Variable increments by this amount each iteration
- Loop ends when variable passes value2

**Examples:**
```pseudocode
// Even numbers 0 to 20
FOR i ← 0 TO 20 STEP 2
   OUTPUT i
NEXT i
// Outputs: 0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20

// Odd numbers 1 to 19
FOR i ← 1 TO 19 STEP 2
   OUTPUT i
NEXT i
// Outputs: 1, 3, 5, 7, 9, 11, 13, 15, 17, 19

// Countdown
FOR i ← 10 TO 1 STEP -1
   OUTPUT i
NEXT i
OUTPUT "Blast off!"
// Outputs: 10, 9, 8, 7, 6, 5, 4, 3, 2, 1, Blast off!

// Count in fives
FOR num ← 5 TO 50 STEP 5
   OUTPUT num
NEXT num
// Outputs: 5, 10, 15, 20, 25, 30, 35, 40, 45, 50
```

**Nested FOR Loops:**
```pseudocode
// Multiplication table
FOR row ← 1 TO 10
   FOR col ← 1 TO 10
      OUTPUT row * col, " "
   NEXT col
   OUTPUT ""  // new line
NEXT row

// Fill 2D array
FOR row ← 1 TO 5
   FOR col ← 1 TO 5
      grid[row, col] ← row * col
   NEXT col
NEXT row

// Calculate total with subtotals
total ← 0
FOR row ← 1 TO maxRow
   rowTotal ← 0
   FOR column ← 1 TO 10
      rowTotal ← rowTotal + amount[row, column]
   NEXT column
   OUTPUT "Total for Row ", row, " is ", rowTotal
   total ← total + rowTotal
NEXT row
OUTPUT "The grand total is ", total
```

### 7.2 Post-Condition (REPEAT-UNTIL) Loops

**Purpose:** When loop must execute **at least once**

**Syntax:**
```pseudocode
REPEAT
   <statement(s)>
UNTIL <condition>
```

**Rules:**
- Condition must evaluate to BOOLEAN
- Statements execute FIRST
- Then condition is tested
- If TRUE, loop terminates
- If FALSE, repeats
- **Always executes at least once**

**When to Use:**
- Menu systems (must show menu at least once)
- Input validation (must ask at least once)
- "Do-while" scenarios

**Examples:**
```pseudocode
// Password validation
REPEAT
   OUTPUT "Please enter the password"
   INPUT password
UNTIL password = "Secret"

// Input validation
REPEAT
   OUTPUT "Enter age (1-100): "
   INPUT age
UNTIL age >= 1 AND age <= 100

// Menu system
REPEAT
   OUTPUT "1. Add record"
   OUTPUT "2. Delete record"
   OUTPUT "3. Search"
   OUTPUT "4. Exit"
   INPUT choice
   
   CASE OF choice
      1 : CALL AddRecord()
      2 : CALL DeleteRecord()
      3 : CALL SearchRecord()
      4 : OUTPUT "Goodbye"
      OTHERWISE : OUTPUT "Invalid choice"
   ENDCASE
UNTIL choice = 4

// Calculate factorial
DECLARE n, factorial, counter : INTEGER
INPUT n
factorial ← 1
counter ← 1

REPEAT
   factorial ← factorial * counter
   counter ← counter + 1
UNTIL counter > n

OUTPUT factorial

// Number guessing game
DECLARE guess, target : INTEGER
target ← 42

REPEAT
   OUTPUT "Guess the number: "
   INPUT guess
   IF guess < target THEN
      OUTPUT "Too low"
   ELSEIF guess > target THEN
      OUTPUT "Too high"
   ENDIF
UNTIL guess = target
OUTPUT "Correct!"
```

### 7.3 Pre-Condition (WHILE) Loops

**Purpose:** When condition must be checked **before** execution

**Syntax:**
```pseudocode
WHILE <condition>
   <statement(s)>
ENDWHILE
```

**Rules:**
- Condition must evaluate to BOOLEAN
- Condition tested BEFORE statements
- If TRUE, statements execute
- After execution, condition tested again
- If FALSE, loop terminates
- **May not execute at all** (if initially FALSE)

**When to Use:**
- Unknown number of iterations
- May not need to execute
- File reading (until EOF)
- Event-driven loops

**Examples:**
```pseudocode
// Count down
counter ← 10
WHILE counter > 0
   OUTPUT counter
   counter ← counter - 1
ENDWHILE

// Reduce number
number ← 100
WHILE number > 9
   number ← number - 9
ENDWHILE
OUTPUT "Final value: ", number

// Read file until end
OPENFILE "data.txt" FOR READ
WHILE NOT EOF("data.txt")
   READFILE "data.txt", line
   OUTPUT line
ENDWHILE
CLOSEFILE "data.txt"

// Input validation with early exit
valid ← FALSE
attempts ← 0
WHILE NOT valid AND attempts < 3
   OUTPUT "Enter password: "
   INPUT password
   IF password = "Secret" THEN
      valid ← TRUE
   ELSE
      attempts ← attempts + 1
      OUTPUT "Incorrect. ", 3 - attempts, " attempts left"
   ENDIF
ENDWHILE

IF valid THEN
   OUTPUT "Access granted"
ELSE
   OUTPUT "Account locked"
ENDIF

// Process array until specific value found
found ← FALSE
index ← 1
WHILE NOT found AND index <= 30
   IF studentNames[index] = "Alice" THEN
      found ← TRUE
      OUTPUT "Found at position ", index
   ELSE
      index ← index + 1
   ENDIF
ENDWHILE

IF NOT found THEN
   OUTPUT "Not found"
ENDIF
```

**Comparison of Loop Types:**

| Aspect | FOR | REPEAT-UNTIL | WHILE |
|--------|-----|--------------|-------|
| **When to use** | Known iterations | Must execute once | Check before execute |
| **Condition check** | Automatic | After statements | Before statements |
| **Minimum executions** | 0 (if start > end) | 1 | 0 |
| **Typical use** | Arrays, counting | Menus, validation | Files, unknown count |

**Example showing difference:**
```pseudocode
// FOR - may not execute if counter > 10
FOR counter ← 11 TO 10
   OUTPUT counter  // Never executes
NEXT counter

// WHILE - may not execute
counter ← 11
WHILE counter <= 10
   OUTPUT counter  // Never executes
   counter ← counter + 1
ENDWHILE

// REPEAT - always executes once
counter ← 11
REPEAT
   OUTPUT counter  // Executes once (outputs 11)
   counter ← counter + 1
UNTIL counter > 10
```

---

## 8. Procedures and Functions

### 8.1 Defining and Calling Procedures

**What is a Procedure?**
- Named block of code that performs a task
- Can be called multiple times
- May have parameters
- Does NOT return a value (or returns via reference parameters)

**Procedure without Parameters:**

**Syntax:**
```pseudocode
PROCEDURE <identifier>()
   <statement(s)>
ENDPROCEDURE
```

**Examples:**
```pseudocode
PROCEDURE DisplayWelcome()
   OUTPUT "Welcome to the program"
   OUTPUT "Please follow the instructions"
ENDPROCEDURE

PROCEDURE PrintSeparator()
   OUTPUT "========================"
ENDPROCEDURE

PROCEDURE ClearScreen()
   // statements to clear screen
ENDPROCEDURE
```

**Calling Procedure (no parameters):**
```pseudocode
CALL <identifier>()

// Examples
CALL DisplayWelcome()
CALL PrintSeparator()
CALL ClearScreen()
```

**Procedure with Parameters:**

**Syntax:**
```pseudocode
PROCEDURE <identifier>(<param1> : <data type>, <param2> : <data type>, ...)
   <statement(s)>
ENDPROCEDURE
```

**Examples:**
```pseudocode
PROCEDURE DisplayGreeting(name : STRING)
   OUTPUT "Hello ", name
   OUTPUT "Welcome to the system"
ENDPROCEDURE

PROCEDURE DisplayGreeting(name : STRING, age : INTEGER)
   OUTPUT "Hello ", name
   OUTPUT "You are ", age, " years old"
ENDPROCEDURE

PROCEDURE DisplayRectangleArea(length : REAL, width : REAL)
   DECLARE area : REAL
   area ← length * width
   OUTPUT "Area = ", area
ENDPROCEDURE

PROCEDURE MoveForward(distance : INTEGER)
   // Move character forward by distance
ENDPROCEDURE

PROCEDURE Turn(angle : INTEGER)
   // Turn character by angle degrees
ENDPROCEDURE
```

**Calling Procedure (with parameters):**
```pseudocode
CALL <identifier>(value1, value2, ...)

// Examples
CALL DisplayGreeting("Alice")
CALL DisplayGreeting("Bob", 25)
CALL DisplayRectangleArea(5.0, 3.0)
CALL MoveForward(100)
CALL Turn(90)

// With variables
DECLARE userName : STRING
DECLARE userAge : INTEGER
userName ← "Charlie"
userAge ← 30
CALL DisplayGreeting(userName, userAge)
```

**Complete Example:**
```pseudocode
// Define procedures
PROCEDURE DefaultSquare()
   CALL Square(100)
ENDPROCEDURE

PROCEDURE Square(size : INTEGER)
   FOR side ← 1 TO 4
      CALL MoveForward(size)
      CALL Turn(90)
   NEXT side
ENDPROCEDURE

// Main program
DECLARE size : INTEGER
CONSTANT Default = 100

INPUT size

IF size = Default THEN
   CALL DefaultSquare()
ELSE
   CALL Square(size)
ENDIF
```

### 8.2 Defining and Calling Functions

**What is a Function?**
- Named block of code that performs calculation
- **Returns a single value**
- Used in expressions
- Must have RETURN statement

**Function without Parameters:**

**Syntax:**
```pseudocode
FUNCTION <identifier>() RETURNS <data type>
   <statement(s)>
   RETURN <value>
ENDFUNCTION
```

**Examples:**
```pseudocode
FUNCTION GetPI() RETURNS REAL
   RETURN 3.14159
ENDFUNCTION

FUNCTION GetTaxRate() RETURNS REAL
   RETURN 0.20
ENDFUNCTION

FUNCTION GetMaxStudents() RETURNS INTEGER
   RETURN 30
ENDFUNCTION
```

**Function with Parameters:**

**Syntax:**
```pseudocode
FUNCTION <identifier>(<param1> : <data type>, <param2> : <data type>, ...) 
    RETURNS <data type>
   <statement(s)>
   RETURN <value>
ENDFUNCTION
```

**Examples:**
```pseudocode
FUNCTION CalculateArea(length : REAL, width : REAL) RETURNS REAL
   DECLARE area : REAL
   area ← length * width
   RETURN area
ENDFUNCTION

FUNCTION Max(number1 : INTEGER, number2 : INTEGER) RETURNS INTEGER
   IF number1 > number2 THEN
      RETURN number1
   ELSE
      RETURN number2
   ENDIF
ENDFUNCTION

FUNCTION IsValidAge(age : INTEGER) RETURNS BOOLEAN
   IF age >= 0 AND age <= 120 THEN
      RETURN TRUE
   ELSE
      RETURN FALSE
   ENDIF
ENDFUNCTION

FUNCTION CalculateGrade(score : INTEGER) RETURNS CHAR
   IF score >= 90 THEN
      RETURN 'A'
   ELSEIF score >= 80 THEN
      RETURN 'B'
   ELSEIF score >= 70 THEN
      RETURN 'C'
   ELSEIF score >= 60 THEN
      RETURN 'D'
   ELSE
      RETURN 'F'
   ENDIF
ENDFUNCTION

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
```

**Calling Functions:**

**Important:** Do NOT use CALL keyword with functions!

Functions are called **within expressions**:

```pseudocode
// Assign return value to variable
circumference ← 2 * GetPI() * radius
area ← CalculateArea(5.0, 3.0)
largest ← Max(10, 25)
grade ← CalculateGrade(85)

// Use in OUTPUT
OUTPUT "Area: ", CalculateArea(10.0, 5.0)
OUTPUT "Penalty Fine = ", Max(10, distance * 2)

// Use in conditions
IF IsValidAge(userAge) THEN
   OUTPUT "Valid"
ENDIF

IF Max(score1, score2) > 100 THEN
   OUTPUT "Exceptional"
ENDIF

// Use in calculations
total ← CalculateArea(5.0, 3.0) + CalculateArea(2.0, 4.0)
average ← (Max(a, b) + Max(c, d)) / 2
```

**RETURN Statement Rules:**
- RETURN immediately exits function
- Code after RETURN is not executed
- Can have multiple RETURN statements
- At least one RETURN must execute

**Example with multiple returns:**
```pseudocode
FUNCTION GetDiscount(price : REAL, memberType : STRING) RETURNS REAL
   IF memberType = "Gold" THEN
      RETURN price * 0.20  // Exit here for Gold
   ELSEIF memberType = "Silver" THEN
      RETURN price * 0.10  // Exit here for Silver
   ELSE
      RETURN 0  // Exit here for others
   ENDIF
   // This line never executes
ENDFUNCTION
```

### 8.3 Passing Parameters by Value or by Reference

**Two Methods of Passing Parameters:**

#### **Pass by Value (BYVAL) - Default**

**How it works:**
- A **copy** of the value is passed
- Changes inside procedure/function **don't affect** original
- Original variable remains unchanged
- Default method if not specified

**Syntax:**
```pseudocode
PROCEDURE <identifier>(BYVAL <param> : <data type>, ...)
   <statement(s)>
ENDPROCEDURE
```

**Example:**
```pseudocode
PROCEDURE IncrementByValue(BYVAL number : INTEGER)
   number ← number + 1
   OUTPUT "Inside procedure: ", number
ENDPROCEDURE

// Main program
DECLARE x : INTEGER
x ← 5
OUTPUT "Before: ", x  // Outputs: 5
CALL IncrementByValue(x)  // Inside outputs: 6
OUTPUT "After: ", x   // Outputs: 5 (unchanged!)
```

#### **Pass by Reference (BYREF)**

**How it works:**
- The **memory address** is passed
- Changes inside procedure **DO affect** original
- Original variable is modified
- Must use BYREF keyword

**Syntax:**
```pseudocode
PROCEDURE <identifier>(BYREF <param> : <data type>, ...)
   <statement(s)>
ENDPROCEDURE
```

**Example:**
```pseudocode
PROCEDURE IncrementByReference(BYREF number : INTEGER)
   number ← number + 1
   OUTPUT "Inside procedure: ", number
ENDPROCEDURE

// Main program
DECLARE x : INTEGER
x ← 5
OUTPUT "Before: ", x  // Outputs: 5
CALL IncrementByReference(x)  // Inside outputs: 6
OUTPUT "After: ", x   // Outputs: 6 (changed!)
```

**Classic Example - SWAP:**
```pseudocode
PROCEDURE Swap(BYREF x : INTEGER, y : INTEGER)
   DECLARE temp : INTEGER
   temp ← x
   x ← y
   y ← temp
ENDPROCEDURE

// Main program
DECLARE a, b : INTEGER
a ← 10
b ← 20

OUTPUT "Before: a=", a, " b=", b  // 10, 20
CALL Swap(a, b)
OUTPUT "After: a=", a, " b=", b   // 20, 10
```

**Multiple Parameters - Mixed:**
```pseudocode
// First parameter by reference, second by value
PROCEDURE UpdateScore(BYREF score : INTEGER, bonus : INTEGER)
   score ← score + bonus
ENDPROCEDURE

DECLARE playerScore : INTEGER
DECLARE bonusPoints : INTEGER

playerScore ← 100
bonusPoints ← 50

CALL UpdateScore(playerScore, bonusPoints)
OUTPUT playerScore  // 150 (changed)
OUTPUT bonusPoints  // 50 (unchanged)
```

**IMPORTANT:**
- If BYVAL/BYREF not specified, **BYVAL is assumed**
- Parameters should **NOT be passed by reference to functions**
- Use BYREF when you need to modify original value
- Use BYVAL when you don't want to change original

**When to Use Each:**

| Use BYVAL when: | Use BYREF when: |
|----------------|----------------|
| Don't want to change original | Need to change original |
| Just reading value | Modifying variable |
| Protecting data | Returning multiple values |
| Most function parameters | Swap operations |
| Simple calculations | Updating records |

---

## 9. File Handling

### 9.1 Handling Text Files

**What are Text Files?**
- Files containing lines of text
- Read/written as strings
- Processed line by line sequentially

**File Modes:**
- **READ** - Read data from file
- **WRITE** - Write to file (creates new or overwrites existing)
- **APPEND** - Add data to end of file

#### **Opening Files**

**Syntax:**
```pseudocode
OPENFILE <file identifier> FOR <file mode>
```

**Examples:**
```pseudocode
OPENFILE "data.txt" FOR READ
OPENFILE "output.txt" FOR WRITE
OPENFILE "log.txt" FOR APPEND

// Using variable for filename
DECLARE fileName : STRING
fileName ← "students.txt"
OPENFILE fileName FOR READ
```

#### **Reading from Files**

**Syntax:**
```pseudocode
READFILE <file identifier>, <variable>
```

- Variable must be STRING
- Reads one line at a time
- File must be open in READ mode

**Examples:**
```pseudocode
DECLARE lineOfText : STRING

OPENFILE "data.txt" FOR READ
READFILE "data.txt", lineOfText
OUTPUT lineOfText
CLOSEFILE "data.txt"
```

#### **EOF Function**

**Syntax:**
```pseudocode
EOF(<file identifier>)
```

- Returns TRUE if no more lines to read
- Returns TRUE if empty file opened
- Returns FALSE otherwise
- Used to check end of file

**Example:**
```pseudocode
OPENFILE "data.txt" FOR READ
WHILE NOT EOF("data.txt")
   READFILE "data.txt", lineOfText
   OUTPUT lineOfText
ENDWHILE
CLOSEFILE "data.txt"
```

#### **Writing to Files**

**Syntax:**
```pseudocode
WRITEFILE <file identifier>, <data>
```

- File must be open in WRITE or APPEND mode
- Writes one line at a time

**Examples:**
```pseudocode
OPENFILE "output.txt" FOR WRITE
WRITEFILE "output.txt", "Hello World"
WRITEFILE "output.txt", "This is line 2"
CLOSEFILE "output.txt"

// Write variable content
DECLARE message : STRING
message ← "Important data"
OPENFILE "log.txt" FOR APPEND
WRITEFILE "log.txt", message
CLOSEFILE "log.txt"
```

#### **Closing Files**

**Syntax:**
```pseudocode
CLOSEFILE <file identifier>
```

- Always close files when finished
- Releases resources
- Ensures data is saved

#### **Complete Examples**

**Example 1: Copy file with modifications**
```pseudocode
DECLARE lineOfText : STRING

OPENFILE "FileA.txt" FOR READ
OPENFILE "FileB.txt" FOR WRITE

WHILE NOT EOF("FileA.txt")
   READFILE "FileA.txt", lineOfText
   IF lineOfText = "" THEN
      WRITEFILE "FileB.txt", "----------------------------"
   ELSE
      WRITEFILE "FileB.txt", lineOfText
   ENDIF
ENDWHILE

CLOSEFILE "FileA.txt"
CLOSEFILE "FileB.txt"
```

**Example 2: Count lines in file**
```pseudocode
DECLARE line : STRING
DECLARE count : INTEGER

count ← 0
OPENFILE "data.txt" FOR READ

WHILE NOT EOF("data.txt")
   READFILE "data.txt", line
   count ← count + 1
ENDWHILE

CLOSEFILE "data.txt"
OUTPUT "Number of lines: ", count
```

**Example 3: Search file for text**
```pseudocode
DECLARE line : STRING
DECLARE searchTerm : STRING
DECLARE found : BOOLEAN

INPUT searchTerm
found ← FALSE

OPENFILE "data.txt" FOR READ

WHILE NOT EOF("data.txt") AND NOT found
   READFILE "data.txt", line
   IF line = searchTerm THEN
      found ← TRUE
      OUTPUT "Found!"
   ENDIF
ENDWHILE

CLOSEFILE "data.txt"

IF NOT found THEN
   OUTPUT "Not found"
ENDIF
```

**Example 4: Write array to file**
```pseudocode
DECLARE students : ARRAY[1:30] OF STRING
DECLARE i : INTEGER

// Fill array (assume already done)

OPENFILE "students.txt" FOR WRITE

FOR i ← 1 TO 30
   WRITEFILE "students.txt", students[i]
NEXT i

CLOSEFILE "students.txt"
```

**Example 5: Read file into array**
```pseudocode
DECLARE scores : ARRAY[1:100] OF INTEGER
DECLARE line : STRING
DECLARE index : INTEGER

index ← 1
OPENFILE "scores.txt" FOR READ

WHILE NOT EOF("scores.txt") AND index <= 100
   READFILE "scores.txt", line
   scores[index] ← INT(line)  // Convert string to integer
   index ← index + 1
ENDWHILE

CLOSEFILE "scores.txt"
```

### 9.2 Handling Random Files

**What are Random Files?**
- Files with records of **fixed length**
- Can access any record directly
- Uses **file pointer** to navigate
- More efficient for large files

**File Pointer:**
- Points to specific location/address in file
- Can be moved to any record
- Record at pointer can be read or written

#### **Opening Random Files**

**Syntax:**
```pseudocode
OPENFILE <file identifier> FOR RANDOM
```

**Example:**
```pseudocode
OPENFILE "StudentFile.dat" FOR RANDOM
```

#### **SEEK Command**

**Purpose:** Move file pointer to specific record

**Syntax:**
```pseudocode
SEEK <file identifier>, <address>
```

- Address is usually record number (position from start)
- Address must be INTEGER expression

**Examples:**
```pseudocode
SEEK "StudentFile.dat", 1    // Go to first record
SEEK "StudentFile.dat", 10   // Go to 10th record
SEEK "StudentFile.dat", position + 1  // Go to next
```

#### **GETRECORD Command**

**Purpose:** Read record at file pointer

**Syntax:**
```pseudocode
GETRECORD <file identifier>, <variable>
```

- Variable must be appropriate data type (usually user-defined type)
- Reads record at current file pointer position

**Example:**
```pseudocode
DECLARE pupil : StudentRecord

SEEK "StudentFile.dat", 5
GETRECORD "StudentFile.dat", pupil
OUTPUT pupil.lastName
```

#### **PUTRECORD Command**

**Purpose:** Write record at file pointer

**Syntax:**
```pseudocode
PUTRECORD <file identifier>, <variable>
```

- Replaces existing data at that position
- Variable contains data to write

**Example:**
```pseudocode
DECLARE newPupil : StudentRecord

newPupil.lastName ← "Johnson"
newPupil.firstName ← "Leroy"

SEEK "StudentFile.dat", 10
PUTRECORD "StudentFile.dat", newPupil
```

#### **Complete Example**

**Move records and insert new one:**

```pseudocode
// Using StudentRecord type from Section 4
DECLARE pupil : StudentRecord
DECLARE newPupil : StudentRecord
DECLARE position : INTEGER

// Prepare new record
newPupil.lastName ← "Johnson"
newPupil.firstName ← "Leroy"
newPupil.dateOfBirth ← 02/01/2005
newPupil.yearGroup ← 6
newPupil.formGroup ← 'A'

OPENFILE "StudentFile.dat" FOR RANDOM

// Move records 10-20 to next position (backwards to avoid overwriting)
FOR position ← 20 TO 10 STEP -1
   SEEK "StudentFile.dat", position
   GETRECORD "StudentFile.dat", pupil
   
   SEEK "StudentFile.dat", position + 1
   PUTRECORD "StudentFile.dat", pupil
NEXT position

// Insert new record at position 10
SEEK "StudentFile.dat", 10
PUTRECORD "StudentFile.dat", newPupil

CLOSEFILE "StudentFile.dat"
```

**Example: Update specific record**
```pseudocode
DECLARE student : StudentRecord
DECLARE recordNum : INTEGER

INPUT recordNum

OPENFILE "StudentFile.dat" FOR RANDOM

// Read record
SEEK "StudentFile.dat", recordNum
GETRECORD "StudentFile.dat", student

// Update
student.yearGroup ← student.yearGroup + 1

// Write back
SEEK "StudentFile.dat", recordNum
PUTRECORD "StudentFile.dat", student

CLOSEFILE "StudentFile.dat"
```

**Text Files vs Random Files:**

| Aspect | Text Files | Random Files |
|--------|-----------|--------------|
| **Access** | Sequential | Direct/Random |
| **Structure** | Lines of text | Fixed-length records |
| **Speed** | Slower for large files | Faster for specific records |
| **Use case** | Simple data, logs | Databases, frequent updates |
| **Commands** | READFILE, WRITEFILE | GETRECORD, PUTRECORD, SEEK |

---

## 10. Object-Oriented Programming

### 10.1 Methods and Properties

**Access Levels:**
- **PUBLIC** - Accessible from outside the class
- **PRIVATE** - Only accessible within the class
- If not specified, assume PUBLIC

**Declaring Properties:**
```pseudocode
PRIVATE <identifier> : <data type>
PUBLIC <identifier> : <data type>
```

**Examples:**
```pseudocode
PRIVATE attempts : INTEGER
PRIVATE name : STRING
PUBLIC score : INTEGER
```

**Defining Methods:**
```pseudocode
PUBLIC PROCEDURE <identifier>(<parameters>)
   <statement(s)>
ENDPROCEDURE

PRIVATE FUNCTION <identifier>(<parameters>) RETURNS <data type>
   <statement(s)>
   RETURN <value>
ENDFUNCTION
```

**Example Class Structure:**
```pseudocode
CLASS Player
   PRIVATE attempts : INTEGER
   PRIVATE score : INTEGER
   
   PUBLIC PROCEDURE SetAttempts(number : INTEGER)
      attempts ← number
   ENDPROCEDURE
   
   PRIVATE FUNCTION GetAttempts() RETURNS INTEGER
      RETURN attempts
   ENDFUNCTION
   
   PUBLIC PROCEDURE AddScore(points : INTEGER)
      score ← score + points
   ENDPROCEDURE
ENDCLASS
```

**Calling Methods:**

Use **object.method()** notation:

```pseudocode
// Create object (shown later)
DECLARE player1 : Player

// Call methods
player1.SetAttempts(5)
player1.AddScore(100)

// Call and use function
OUTPUT player1.GetAttempts()
```

### 10.2 Constructors and Inheritance

#### **Constructors**

**What is a Constructor?**
- Special procedure that initializes object
- Always named **NEW**
- Called when object is created

**Syntax:**
```pseudocode
CLASS <ClassName>
   <properties>
   
   PUBLIC PROCEDURE NEW(<parameters>)
      <initialization statements>
   ENDPROCEDURE
ENDCLASS
```

**Example:**
```pseudocode
CLASS Pet
   PRIVATE name : STRING
   
   PUBLIC PROCEDURE NEW(givenName : STRING)
      name ← givenName
   ENDPROCEDURE
   
   PUBLIC
