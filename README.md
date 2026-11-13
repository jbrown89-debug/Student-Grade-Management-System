# Student-Grade-Management-System

# Grade Management System (C++)

A console-based C++ application for managing student names and grades using dynamically allocated parallel arrays, manual memory resizing, input validation, and recursion.

---

## Features

- **Dynamic Memory Management:** Uses raw pointers (`string*` and `double*`) that automatically double in capacity (`0 -> 2 -> 4 -> 8...`) as new students are added.
- **Full CRUD Operations:** Add new student records, display all stored records, update existing grades, and wipe all records from memory.
- **Grade Analytics:** Calculates the class average and finds the highest grade using a recursive algorithm (`findHighestRecursive`).
- **Input Validation:** Guards against non-numeric menu inputs and enforces valid grade ranges (`0` to `100`).
- **Safe Memory Cleanup:** Frees all dynamically allocated heap memory (`delete[]`) on record deletion and program exit.

---

## Prerequisites

- A C++ compiler supporting C++11 or later (`g++`, `clang++`, or MSVC)
- Alternatively, run directly in your browser using [C++ Shell](https://cpp.sh/)

---

## Getting Started

### 1. Save the Code
Save your source code into a file named `main.cpp`.

### 2. Compile the Program
Open a terminal in the same folder as `main.cpp` and run:

```bash
g++ -Wall -std=c++11 main.cpp -o grade_manager
Use code with caution.

3. Run the Program

On Linux / macOS:
bash
./grade_manager
Use code with caution.
On Windows:
bash
grade_manager.exe
Use code with caution.

How to Use

When you launch the program, an interactive menu appears with 7 options:
text
==========================================
   WELCOME TO THE GRADE MANAGEMENT SYSTEM 
==========================================

------------------ MENU ------------------
1. Add New Student Record
2. Display All Student Records
3. Calculate Average Grade
4. Find Highest Grade //(Recursive)//
5. Update a Student's Grade
6. Delete All Records
7. Exit Program
------------------------------------------
Enter your choice (1-7):
Use code with caution.

Option	Action	Details
1
	Add New Student Record	Prompts for the student's full name (supports spaces) and a grade between 0 and 100. Automatically expands array capacity when full.
2
	Display All Student Records	Lists every stored student alongside their grade.
3
	Calculate Average Grade	Computes and displays the mean grade across all students to 2 decimal places.
4
	Find Highest Grade	Recursively scans the grades array and prints the top score.
5
	Update a Student's Grade	Locates an existing student record and updates their stored grade.
6
	Delete All Records	Deallocates the dynamic arrays, resets counters to 0, and sets pointers back to NULL.
7
	Exit Program	Cleans up all remaining heap memory and exits safely.


Usage Examples


Example 1: Adding Students & Validation

text
Enter your choice (1-7): 1

Enter student full name: Maya Lin
Enter student grade (0 - 100): 105
Invalid grade. Please enter a value between 0 and 100: 92.5
[+] Student record added successfully!

Enter your choice (1-7): 1

Enter student full name: Devon Brooks
Enter student grade (0 - 100): 84
[+] Student record added successfully!
Use code with caution.

Example 2: Viewing Records, Average, and Highest Grade

text
Enter your choice (1-7): 2

=========== STUDENT GRADE RECORDS ===========
1. Maya Lin - 92.50%
2. Devon Brooks - 84.00%

Enter your choice (1-7): 3

[+] Class Average Grade: 88.25%

Enter your choice (1-7): 4

[+] Highest Grade in Class: 92.50%
Use code with caution.

Example 3: Clearing Memory and Exiting

text
Enter your choice (1-7): 6

[+] All student records have been deleted and memory freed.

Enter your choice (1-7): 7

Exiting system... Memory cleaned up. Goodbye!
Use code with caution.

Code Architecture


Function	Purpose
displayMenu()
	Prints the main 7-option CLI menu.
resizeArrays(...)
	Doubles array capacity (newCapacity = capacity * 2), copies existing records, and frees old pointers.
addStudent(...)
	Triggers resizeArrays if count == capacity, validates input, and appends a student.
displayRecords(...)
	Read-only traversal (const pointers) of student names and grades.
calculateAverage(...)
	Sums all grades and divides by count.
findHighestRecursive(...)
	Recursively determines the maximum value in the grades array.
updateGrade(...)
	Modifies a student's grade in place.
deleteAllRecords(...)
	Calls delete[] on both arrays and resets count and capacity to 0.


