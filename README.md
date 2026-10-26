# Learner Management System

A menu-driven Python application for registering learners, capturing their marks, and working out their results. It combines a console menu with Tkinter pop-up dialogs for confirmations and error messages.

## Features

- **Add learners** with an ID, name, age and course
- **View, update and delete** learner records
- **Enter marks** for a learner (up to 20 marks, each between 0 and 100)
- **Display marks** for any learner
- **Search** for a learner by ID
- **Show results**: average mark, performance category and certificate eligibility
- **Count** the total number of registered learners

## Requirements

- Python 3.8 or newer
- Tkinter (included with most Python installs)

On some Linux distributions Tkinter has to be installed separately:

```bash
sudo apt install python3-tk
```

## Getting Started

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
python main.py
```

Replace `main.py` with the name of your script file.

## Usage

The program shows a menu in the terminal. Type the number of the option you want and press Enter.

```
========== MENU ==========
1. Add Learner
2. View All Learners
3. Update Learner
4. Delete Learner
5. Enter Marks
6. Display Marks
7. Search Learner
8. Show Results
9. Count Learners
0. Exit
==========================
```

Prompts are answered in the terminal, while success and error messages appear as pop-up windows.

### Example results output

```
========== RESULTS ==========
Learner ID: L001
Name: Thabo
Course: Python Basics
Marks: [65.0, 72.0, 80.0]
Average: 72.33
Performance: Pass
Certificate: Qualified
=============================
```

## Grading Rules

| Average mark | Performance |
|--------------|-------------|
| Below 50 | Fail |
| 50 to 74 | Pass |
| 75 and above | Pass with Distinction |

A learner **qualifies for a certificate** with an average of 50 or higher.

## Validation

- Learner IDs must be unique
- Learners must be at least 10 years old
- Age and the number of marks must be numeric
- Marks outside 0 to 100 are skipped
- No more than 20 marks can be stored per learner
- Menu input must be a valid number

## Project Structure

The project is a single script made up of:

| Component | Description |
|-----------|-------------|
| `Person` | Base class holding a name and age |
| `Learner` | Inherits from `Person`; adds ID, course, marks and a private average |
| `recursive_sum()` | Recursively adds up a list of marks |
| `count_learners()` | Recursively counts the stored learners |
| CRUD functions | `add_learner`, `view_learners`, `update_learner`, `delete_learner` |
| Marks and results | `enter_marks`, `display_marks`, `show_results` |
| `main()` | Runs the menu loop |

## Concepts Demonstrated

- **Inheritance**: `Learner` extends `Person`
- **Encapsulation**: the average mark is private and accessed through getter and setter methods
- **Recursion**: used for summing marks and counting learners
- **Exception handling**: `ValueError` and `ZeroDivisionError` are handled gracefully
- **GUI dialogs**: Tkinter `messagebox` for feedback and exit confirmation

## Known Limitations

- Data is stored in memory only and is lost when the program closes
- Learner IDs are case-sensitive
- Recursive summing is limited by Python's recursion depth (not a concern with the 20-mark cap)

## Future Improvements

- Save and load learners from a file or database (JSON, CSV or SQLite)
- Replace the console menu with a full Tkinter interface
- Add unit tests
- Export results to a report

## Author

Smangaliso Mathebula
[GitHub: SmangalisoMathebula](https://github.com/SmangalisoMathebula)
