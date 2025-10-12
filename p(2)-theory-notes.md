# Revision Notes for Theory Part of Paper-2

## Algorithms

**Algorithm:** A sequence of steps to be followed in the completion of a task.

### Methods to Represent an Algorithm
- Structured English
- Pseudocode
- Flowchart

### Activities Performed by Algorithms
Algorithms usually perform three different activities:
- **Input:** Entering data to a system for processing
- **Process:** Performing calculation or assigning values
- **Output:** Displaying result after processing

### Features Used to Make Pseudocode Easier to Read and Understand
- Indentation
- Using meaningful identifiers
- Annotation or commenting
- Capitalization of keywords
- Putting gaps between lines
- Modularization

---

## Programming Constructs

### Three Main Constructs

**Sequence:** Sequential execution of the instructions.

**Selection:** Determines which path the program control should take based on a condition.

**Iteration:** Repeatedly executing statement or set of statements for a certain number of times or until a condition is satisfied.

---

## Program Design Concepts

### Stepwise Refinement
Process of breaking down a task into series of subtasks from which it becomes easier to program.

### Decomposition/Modularization
Process of breaking down a complex system into smaller parts that are more manageable and easier to understand.

### Benefits of Modularization/Decomposition
- It reduces the complexity of a program since a program is divided into smaller manageable subprograms
- Debugging and testing the program become easier as individual subroutines/modules can be debugged or tested separately
- The subprograms can be reused
- Different programmers get scope to work on same program as a result it reduces the development time

---

## Subroutines

**Subroutine:** A set of statements that can be grouped together and easily called in a program whenever required, rather than repeating all of the statements each time.

### Types of Subroutines

**Function:** It is a subroutine which must return a single value to the calling program.

**Procedure:** It is a subroutine which usually does not return any value to the calling program.

### Library Routine vs User Defined Routine

**Library Routine:** A tested and ready-to-use subroutine available in a programming language that can be incorporated into a program.

**User Defined Routine:** A subroutine written by the user to perform a specific task required by a program.

---

## Advantages and Disadvantages

### Advantages of Using Library Routines
- These are robust (unlikely to fail)
- Saves time
- Available to all programs
- Well tested and tried

### Disadvantages of Using Library Routines
- It cannot be edited
- Decreases the speed of execution slightly

### Advantages of Using User Defined Functions
- These can be reused
- These can be edited
- More specific to the requirement
- Easy to debug and maintain
- Reduces complexity of the program

---

## Built-in vs User Defined Functions

### Similarities Between Built-in and User Defined Functions
- They both have an identifier/name
- They both return a value
- Both have one or more parameters
- Perform a specific task
- Both represent re-usable code
- Both are called

### Differences Between Built-in Function and User Defined Function
- Built-in functions are made available by the programming language / already in the system
- Built-in functions are ready made and tested
- User-defined functions can be modified but built-in functions cannot be modified
- User defined functions can be designed to meet the user's requirements
- User-defined functions can only be used in that program but built-in functions can be used in any program

---

## Parameters and Arguments

**Arguments:** The list of variables used in a calling function.

**Parameters:** The list of variables used in the header of a function definition.

### Explain Why Parameters are Used with Subroutines
- To pass values to/from subroutine
- To avoid using global variables
- To allow recursion
- To make the subroutine re-usable

---

## Parameter Passing Methods

### By Value (ByVal)
Only a copy of the variable is sent as parameter so changes to the value of the variable will not change the variable outside the module.

### By Reference (ByRef)
The address of the variable is passed. Original value of the variable will be changed if any change is made to the variable inside the module.

---

## Scope of Variables

**Local Variable:** The variables which are declared in a subroutine and work within the subroutine.

**Global Variable:** The variables which are declared at the beginning of the program and work in all of the subroutines in that program.

---

## Structure Chart

**Structure Chart:** A chart which shows the breakdown of a system to its lowest manageable levels.

### Features That are Shown on a Structure Chart
- Hierarchy of modules
- Parameters that are passed through each module
- Sequence of module execution
- Selections
- Iterations

---

## Transferable Skills

**Transferable Skill:** Any existing skill that can be used to handle a new situation. Programming is a transferable skill, as skill of a programming language can be used to recognize common features of an unknown programming language. It can be able to recognize variable declarations, data types, assignments, sequence, selection, iteration, modules, etc.

---

## Data Structures

**Data Structure:** A particular way of organizing data in a computer so that it can be used effectively.

### Examples of Data Structures
- Variable
- Constant
- Array
- Stack
- Queue
- Linked List
- Binary Tree
- Graph
- Hash Table

---

## Integrated Development Environment (IDE)

### Features of IDE

#### For Presentation
- **Pretty printing:** Different color coding of keywords
- **Auto indentation**
- **Expansion and collapse blocks:** Display or hide blocks of code by choice
- **Auto-completion:** Shows keywords and available identifiers appropriate at current insertion point and provides choices in alphabetical order

#### For Initial Error Detection
- **Breakpoint:** Stops execution at a specific line
- **Dynamic syntax check:** Automatic checking and highlighting of syntax errors, as soon as line is typed
- **Type checking**
- **Checking for unused variables that are declared / checking for used variables which are not declared**

#### For Debugging
- **Breakpoint:** Pauses program at a specific line to ensure program operates correctly up to the line
- **Single stepping:** Executes program line-by-line to see the effect of each statement on variables
- **Variables/Expressions Report or Watch Window:** Monitors variables for comparing values

---

## Software Development Life Cycle (SDLC)

**Purpose of a Development Life Cycle:** The process of developing a program set out in five stages: analysis, design, coding, testing, maintenance.

### Five Stages of SDLC

#### 1. Analysis
Process of investigation, leading to specification of what the program is required to do.

Methods used in Analysis:
- Face to face interview
- Observation
- Questionnaire
- Analyzing manual documents

#### 2. Design
Develop logic plan, using the analysis.

Activities in Design:
- Designing file structure
- Designing input/output screen
- Designing algorithm
- Designing test plan

#### 3. Coding
The writing of the program.

#### 4. Testing
The testing of the program to make sure it works under all conditions.

#### 5. Maintenance
Ensuring the program continues to work during use.

---

## Software Development Models

There are three different models that can be used in software development:
1. Waterfall Model
2. Iterative Model
3. Rapid Application Development (RAD)

---

## 1. Waterfall Model

**Waterfall Model:** A linear sequential program development cycle, in which each stage is completed before the next is begun.

### Benefits of Waterfall Model
- Easier to manage, understand and use
- Stages do not overlap and are completed one at a time
- Each stage has specific outcomes
- Works well for smaller programs where requirements are known and understood

### Drawbacks of Waterfall Model
- Difficult to change the requirements at a later stage
- Working program is produced late in the life cycle
- Not suitable for long, complex projects

---

## 2. Iterative Model

**Iterative Model:** An initial representation starts with a small subset, which becomes more complex over time until the system is complete.

### Benefits of Iterative Model
- Some working programs developed quickly at an early stage
- Easier to test and debug smaller programs
- More flexible as easier to alter requirements
- Customer involved in each iteration then no surprises when final system is delivered

### Drawbacks of Iterative Model
- Whole program needs to be designed at start, so it can be broken down into modules to be developed at each iteration
- Not suitable for short simple projects
- More resources might be required
- Needs good planning for every stage

---

## 3. Rapid Application Development (RAD)

**Rapid Application Development (RAD):** A planning model, with no (or less) specific planning put into it. More emphasis on development and producing a product prototype. A prototype is a working model of part of the intended system. High customer involvement, as customer can use the prototypes during development.

### Benefits of RAD
- Reduced overall development time
- Quick initial reviews occur
- Very flexible as requirements are met from the feedbacks of customers
- Modification is easier

### Drawbacks of RAD
- Requires skilled developers
- Only systems that are modularized can be built using RAD
- Not suitable for short simple projects

---

## Types of Errors

### 1. Syntax Error
When source code does not obey rules of the language.

### 2. Logical Error
Program works but gives incorrect output due to incorrect logical/arithmetical statements.

### 3. Run-time Error
An error found in a program when it is executed.

**Examples of Run-time Errors:**
- Division by 0
- Out of array index/subscript
- Trying to open a file which does not exist

---

## Methods of Testing

### White-box Testing
In this test, all the possible paths of a program are tested.

### Black-box Testing
In this test, the expected outcomes is checked against actual outcomes.

### Alpha Testing
The testing which is carried out by technical persons who were not involved in the program development. It is usually done in development stage.

### Beta Testing
The testing of a completed program by a small group of users before it is released.

### Stub Testing
Testing the main program without completing the codes of the subroutines. There dummy messages/returning values are given as body of the subroutines to indicate that the subroutine is used.

### Integration Testing
Taking modules that have been tested individually and testing them combined together.

### Acceptance Testing
A test carried out by the intended users of the system, the people who requested the software. It is used to prove to the client that the software works exactly as required.

---

## Types of Test Data

**Example Range:** Values between 1 to 100 (inclusive)

### Normal Data
Any values between 1 to 100 (inclusive) - valid values within the expected range.

### Abnormal Data
Any values out of the range of 1 to 100 - invalid values.

### Extreme Data
The upper and lower bounds: 1 and 100.

### Boundary Data
Immediate upper or lower value from the range like 0 and 101. They are rejected.

---

## Manual Debugging Tools

### Dry Run/Tracing
A process where code is manually traced, without any software used.

### Walkthrough
A formal version of a dry run, done by team members etc.

---

## Types of Maintenance

### 1. Corrective Maintenance
To correct any errors in a program that appear during use.

### 2. Adaptive Maintenance
The alteration of a program to append some new requirements.

### 3. Perfective Maintenance
Process of making improvements to make a program more efficient.

---

## Summary

These notes cover all the essential topics for the theory part of Paper-2, including:
- Algorithms and their representation
- Programming constructs (sequence, selection, iteration)
- Modularization and decomposition
- Subroutines (functions and procedures)
- Parameters and variable scope
- Data structures
- IDE features
- Software Development Life Cycle (SDLC)
- Development models (Waterfall, Iterative, RAD)
- Error types and testing methods
- Test data types
- Program maintenance
