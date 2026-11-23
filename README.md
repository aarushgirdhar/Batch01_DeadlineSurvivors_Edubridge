# EduBridge Learning System

## 1. Project Title

**EduBridge Learning System – Student Performance Analysis and Quiz System**

---

## 2. Problem Statement

Students need an easy and systematic way to record academic performance, test their understanding of different subjects, and identify areas where improvement is required.

The **EduBridge Learning System** is a console-based application developed using the **C programming language**. It allows students to register, view subjects, enter marks, attempt subject-wise quizzes, analyse their academic performance, identify weak and strong areas, and view saved results.

The project demonstrates the practical implementation of fundamental C programming concepts including structures, arrays, functions, loops, conditional statements, switch statements, multidimensional arrays, string handling, input validation, and file handling.

---

## 3. Team Details

**Team Number:** 8  
**Batch:** 1

| S. No. | Team Member |
|---|---|
| 1 | **Aarush Girdhar** |
| 2 | **Lakshay Rathi** |
| 3 | **Ishika Malik** |

---

## 4. Objectives

The objectives of the project are:

1. To develop a menu-driven learning system using C.
2. To register and store student information.
3. To record marks for five academic subjects.
4. To conduct subject-wise multiple-choice quizzes.
5. To calculate subject-wise and overall quiz scores.
6. To calculate the student's overall academic percentage.
7. To classify performance as Weak, Average, or Strong.
8. To identify subjects requiring improvement.
9. To provide subject-specific improvement suggestions.
10. To identify strong academic areas.
11. To store student details and results using file handling.
12. To provide safe input validation.

---

# 5. Features of the Program

### Student Registration

The program accepts the student's:

- Student ID
- Student Name
- Course

Registration information is stored in `students.txt`.

### View Subjects

Five subjects are available:

1. C Programming
2. Maths
3. Physics
4. Problem Solving
5. EVS

### Enter Subject Marks

Marks between **0 and 100** can be entered for each subject. Invalid values are rejected.

### Subject Quiz

Each of the five subjects contains **5 multiple-choice questions**.

**Total Questions = 5 × 5 = 25**

The program calculates:

- Subject-wise score
- Total score out of 25
- Overall quiz percentage

### Performance Analysis

| Marks | Performance |
|---:|---|
| Below 40 | Weak |
| 40–59 | Average |
| 60–100 | Strong |

The program also identifies areas needing improvement and strong areas.

### File Handling

Two files are used:

- `students.txt` – stores registration information.
- `results.txt` – stores marks and quiz results.

---

# 6. Algorithm

1. Start the program.
2. Initialize student data, marks, quiz scores, and status variables.
3. Display the main menu.
4. Accept and validate the user's choice.
5. If choice is **1**, register the student.
6. If choice is **2**, display the subjects.
7. If choice is **3**, check registration and enter subject marks.
8. If choice is **4**, check registration and marks, then conduct all quizzes.
9. If choice is **5**, check marks and quiz completion, then analyse performance.
10. If choice is **6**, read and display saved results.
11. If choice is **7**, display the exit message.
12. Return to the main menu while the choice is not 7.
13. End.

---

# 7. Pseudocode

```text
BEGIN

SET registered = 0
SET marksEntered = 0
SET quizTaken = 0
INITIALIZE student data and quiz scores

REPEAT

    DISPLAY Main Menu
    INPUT choice

    SWITCH choice

        CASE 1:
            INPUT Student ID
            INPUT Student Name
            INPUT Course
            SET registered = 1
            RESET marks and quiz scores
            SAVE details to students.txt

        CASE 2:
            DISPLAY all five subjects

        CASE 3:
            IF registered = 0
                DISPLAY "Please register first!"
            ELSE
                FOR each subject
                    INPUT marks from 0 to 100
                END FOR
                SET marksEntered = 1
                SAVE marks to results.txt
            END IF

        CASE 4:
            IF registered = 0
                DISPLAY "Please register first!"
            ELSE IF marksEntered = 0
                DISPLAY "Please enter subject marks first!"
            ELSE
                FOR each subject
                    SET score = 0

                    FOR each question
                        DISPLAY question and options
                        INPUT answer

                        IF answer is correct
                            score = score + 1
                        END IF
                    END FOR

                    STORE subject score
                END FOR

                CALCULATE total quiz score
                CALCULATE quiz percentage
                SET quizTaken = 1
                SAVE quiz results
            END IF

        CASE 5:
            IF marksEntered = 0
                DISPLAY "Please enter marks first!"
            ELSE IF quizTaken = 0
                DISPLAY "Please complete all quizzes first!"
            ELSE
                FOR each subject

                    IF marks < 40
                        CLASSIFY as Weak
                    ELSE IF marks < 60
                        CLASSIFY as Average
                    ELSE
                        CLASSIFY as Strong
                    END IF

                    IF marks < 40 OR quiz score <= 2
                        DISPLAY improvement suggestions
                    END IF

                    IF marks >= 60 AND quiz score >= 3
                        DISPLAY strong-area suggestions
                    END IF

                END FOR

                CALCULATE overall percentage
                DISPLAY performance summary
            END IF

        CASE 6:
            OPEN results.txt

            IF file exists
                DISPLAY saved results
            ELSE
                DISPLAY "No saved results available!"
            END IF

        CASE 7:
            DISPLAY "Thank you for using EduBridge!"

    END SWITCH

UNTIL choice = 7

END
```

---

# 8. Flowchart

The detailed program flowchart is provided separately as:

**`EduBridge_Flowchart.png`**

Basic program flow:

```text
START
  │
  ▼
Initialize Program
  │
  ▼
Display Main Menu
  │
  ▼
Read User Choice
  │
  ▼
┌───────────────────────────────┐
│         Menu Choice           │
└───────────────────────────────┘
  │
  ├── 1 → Student Registration
  │
  ├── 2 → View Subjects
  │
  ├── 3 → Enter Subject Marks
  │
  ├── 4 → Take All Quizzes
  │
  ├── 5 → Analyse Performance
  │
  ├── 6 → View Results
  │
  └── 7 → Exit
              │
              ▼
         Choice = 7?
          /       \
        NO         YES
        │           │
        ▼           ▼
    Main Menu      END
```

---

# 9. C Programming Concepts Used

| Concept | Use in Project |
|---|---|
| Structures | Stores student ID, name, course, and marks |
| Arrays | Stores subjects, marks, and quiz scores |
| Multidimensional Arrays | Stores quiz questions, options, and answers |
| Functions | Divides the program into reusable modules |
| `for` Loops | Processes subjects, questions, marks, and scores |
| `while` Loop | Used for input validation |
| `do-while` Loop | Repeats the main menu |
| `if-else` | Validation and performance classification |
| `switch` | Main menu and subject recommendations |
| Strings | Stores student name, course, questions, and options |
| File Handling | Saves registration, marks, and quiz results |
| Pointers | Used by `strtol()` for input validation |

### Major Functions

| Function | Purpose |
|---|---|
| `readInt()` | Reads and validates integers |
| `readLine()` | Reads text input |
| `registration()` | Registers the student |
| `viewSubjects()` | Displays subjects |
| `enterMarks()` | Accepts and stores marks |
| `takeQuiz()` | Conducts the quizzes |
| `analysePerformance()` | Analyses performance |
| `viewResult()` | Displays saved results |
| `main()` | Controls the program |

---

# 10. Compilation and Execution

## Requirements

A C compiler such as **GCC**
