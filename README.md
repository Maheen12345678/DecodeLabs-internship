# DecodeLabs Python Programming Projects

This repository contains my Python programming projects completed as part of the **DecodeLabs Industrial Training Program – Batch 2026**. The projects were designed to develop practical Python programming skills through hands-on implementation of real-world applications.

## Projects Included

| Project | Title | Main Concepts |
|---|---|---|
| Project 1 | To-Do List | Lists, `append()`, `enumerate()`, functions, JSON persistence |
| Project 2 | Expense Tracker | Variables, loops, input handling, arithmetic, accumulators |
| Project 3 | Random Password Generator | `random`, `string`, loops, string manipulation, password generation |
| Project 4 | General Knowledge Quiz | If-Else logic, variables, control flow, string sanitization |

---

## 📁 Project 1 – To-Do List

### 🎯 Objective
The goal of Project 1 is to build a simple To-Do List application where users can add tasks, view their tasks, and delete tasks. The application also saves the tasks to a JSON file so that the task list can be loaded again when the program is restarted.

### 🧠 Key Concepts
This project demonstrates:
- Python Lists
- `append()`
- `pop()`
- `enumerate()`
- Functions
- `if`/`elif`/`else`
- `while` loops
- User input
- Exception handling
- JSON File handling
- Basic data persistence

### ✨ Features

**1. Add Task**
Users can enter a new task.
```
Enter a new task: Complete Python assignment
Added: "Complete Python assignment"
```
The task is added to the list using:
```python
my_tasks.append(task)
```

**2. View Tasks**
The program displays all saved tasks with numbers.
```
--- Your To-Do List ---
1. Complete Python assignment
2. Study Python
3. Upload project to GitHub
------------------------
```
The `enumerate()` function is used to display task numbers.

**3. Delete Task**
Users can enter the number of a task they want to remove.
```
Enter the task number to delete: 2
Removed: "Study Python"
```
The task is removed using:
```python
my_tasks.pop(choice - 1)
```

**4. Persistent Storage**
Tasks are stored in: `tasks.json`
The program uses the `json` module to save and load tasks. This means tasks can remain available even after the program is closed and reopened.

### 🔄 Program Flow
```
Start
  ↓
Load saved tasks
  ↓
Display menu
  ↓
Choose an option
  ↓
┌───────────────┐
│               │
Add Task     View Tasks
  │               │
Save Task    Display Tasks
  │               │
  └───────┐       │
      Delete Task  │
          ↓        │
      Save Tasks    │
          ↓
        Exit
```

### 🛠️ Technologies
- Python 3
- JSON File Handling

---

## 💰 Project 2 – Expense Tracker

### 🎯 Objective
The goal of Project 2 is to create an Expense Tracker that allows users to enter multiple expense amounts and calculates the total amount spent. The project focuses on mathematical operations and accumulators.

### 🧠 Key Concept – Accumulator
The main concept of this project is an accumulator. The program starts with:
```python
total = 0
```
Each new expense is then added to the existing total:
```python
total = total + expense
```
For example:
```
Expense 1 = 100
Expense 2 = 50
Expense 3 = 20
Total = 100 + 50 + 20 = 170
```
The final result is:
```
Total Spent: 170.0
```

### ✨ Features
1. **Multiple Expenses** – The user can enter multiple expense amounts.
2. **Running Total** – The program displays the updated total after each expense.
3. **Exit Command** – The user can type `done` to finish entering expenses.
4. **Decimal Expenses** – The program accepts decimal values such as `100.50`, `25.75`, `10.25`.
5. **Invalid Input Handling** – If the user enters something other than a number, the program displays an error message.
6. **Negative Expense Protection** – Negative values are rejected.

### 🧪 Example
**Input**
```
100
50
20
done
```
**Output**
```
Expense added successfully! Current Total Spent: 100.0
Expense added successfully! Current Total Spent: 150.0
Expense added successfully! Current Total Spent: 170.0
Total Spent: 170.0
```

### 🛠️ Technologies
- Python 3
- Google Colab
- User Input
- Loops
- Arithmetic Operations
- Exception Handling

---

## 🔐 Project 3 – Random Password Generator

### 🎯 Objective
The goal of Project 3 is to create a Random Password Generator that asks the user for a desired password length and generates a random password containing letters, numbers, and special characters. The project focuses on importing Python's built-in `random` and `string` modules and using string manipulation.

### 🧠 Key Concepts
This project demonstrates:
- Importing Python modules
- `random`
- `string`
- `random.choice()`
- `random.shuffle()`
- `string.ascii_letters`
- `string.digits`
- Lists
- Loops
- String manipulation
- User input
- Exception handling

### ✨ Features
1. **User-Defined Password Length** – The program asks: `Enter password length:` (e.g. `12`), and generates a password containing 12 characters.
2. **Letters** – Uses `string.ascii_letters` to provide uppercase and lowercase letters.
3. **Numbers** – Uses `string.digits` to provide numbers from 0–9.
4. **Special Characters** – Includes `@ # $ % & * ! ?`.
5. **Minimum Password Length** – The program requires at least 4 characters.
6. **Password Requirements** – The generated password contains at least one letter, one number, and one special character.
7. **Randomization** – Uses `random.choice()` to select characters randomly, then `random.shuffle()` to mix the characters.

### 🧪 Example
**Input**
```
Enter password length: 12
```
**Possible Output**
```
==========================================
PASSWORD GENERATED
==========================================
Your random password is: 7@kP2!mQ9xL$
Password length: 12
==========================================
```
The exact password will be different each time because it is randomly generated.

### 🛠️ Technologies
- Python 3
- `random` module
- `string` module

---

## 🧠 Project 4 – General Knowledge Quiz

### 🎯 Objective
The goal of Project 4 is to build a simple General Knowledge Quiz that asks the user 3 general knowledge questions, keeps a running score (+1 point per correct answer), and prints the final score at the end. The project focuses on `if`/`else` logic and control flow.

### 🧠 Key Concepts
This project demonstrates:
- If-Else logic (control flow)
- Variables and integer accumulators
- Functions
- `for` loops with `enumerate()`
- String sanitization with `.strip()` and `.lower()`
- Dictionaries (question/answer pairs)
- Lists of dictionaries (question bank)
- User input
- f-strings for formatted output

### ✨ Features

**1. Answer Sanitization Pipeline**
Every answer goes through `.strip().lower()` so that extra whitespace and inconsistent capitalization don't cause a correct answer to be marked wrong:
```python
guess = raw_input_answer.strip().lower()
```

**2. Score Tracking (Accumulator)**
`score` is initialized as an integer (`score = 0`) and incremented with `score += 1` only on a correct match. The `else` branch performs no operation on the score — state is maintained, not reset:
```python
if guess == q["answer"]:
    score += 1
else:
    print(f"Wrong! ❌ The correct answer was '{q['answer'].title()}'.")
```

**3. Question Bank**
Questions are stored as a list of dictionaries, each pairing a question with its reference (correct) answer:
```python
questions = [
    {"question": "What is the capital of France? ", "answer": "paris"},
    {"question": "What is the largest planet in our Solar System? ", "answer": "jupiter"},
    {"question": "Who wrote the play 'Romeo and Juliet'? ", "answer": "shakespeare"},
]
```

**4. Numbered Questions**
The program uses `enumerate()` (starting at 1) to number each question as it's asked.

**5. Final Score Output**
The final result is delivered using an f-string:
```python
print(f"Quiz complete! Your final score is {score:>2}/{total}.")
```

### 🔄 Program Flow
```
Start
  ↓
Initialize score = 0
  ↓
For each question in the Question Bank:
  ↓
Ask question (input)
  ↓
Sanitize answer (.strip().lower())
  ↓
   ┌── Correct? ──┐
   │              │
  Yes             No
   │              │
score += 1    Show correct answer
   │              │
   └──────┬───────┘
          ↓
   Next question / End of loop
          ↓
Print final score (f-string)
          ↓
        Exit
```

### 🧪 Example
**Input**
```
Q1: What is the capital of France? paris
Q2: What is the largest planet in our Solar System? mars
Q3: Who wrote the play 'Romeo and Juliet'? Shakespeare
```
**Output**
```
==================================================
WELCOME TO THE GENERAL KNOWLEDGE QUIZ!
==================================================
Answer each question below. Good luck!

Correct! ✅

Wrong! ❌ The correct answer was 'Jupiter'.

Correct! ✅

==================================================
Quiz complete! Your final score is  2/3.
==================================================
```

### 🛠️ Technologies
- Python 3
- Google Colab

---

## 📂 Repository Structure

The repository can be organized as follows:
```
DecodeLabs-Python-Projects/
│
├── README.md
│
├── Project-1-To-Do-List/
│   ├── todo_list.py
│   └── tasks.json
│
├── Project-2-Expense-Tracker/
│   └── expense_tracker.py
│
├── Project-3-Random-Password-Generator/
│   └── password_generator.py
│
└── Project-4-General-Knowledge-Quiz/
    └── quiz.py
```

If all four projects are currently in separate Google Colab notebooks, they can also be stored as:
```
DecodeLabs-Python-Projects/
│
├── README.md
├── Project_1_To_Do_List.ipynb
├── Project_2_Expense_Tracker.ipynb
├── Project_3_Random_Password_Generator.ipynb
└── Project_4_General_Knowledge_Quiz.ipynb
```

## 🚀 How to Run the Projects

**Option 1 – Google Colab**
1. Open Google Colab.
2. Create a new notebook.
3. Copy the code for the desired project.
4. Run the code cell.
5. Follow the instructions displayed by the program.

**Option 2 – Local Python**
Make sure Python 3 is installed. Then run:
```
python todo_list.py
```
or:
```
python expense_tracker.py
```
or:
```
python password_generator.py
```
or:
```
python quiz.py
```

## 📚 Overall Learning Outcomes

By completing these four projects, I developed practical knowledge of fundamental Python programming concepts.

**Project 1 – To-Do List**
I learned how to:
- Create and manipulate lists.
- Add and remove list items.
- Use `enumerate()` to display indexed data.
- Create reusable functions.
- Work with JSON files.
- Save and load data.
- Build a menu-driven application.

**Project 2 – Expense Tracker**
I learned how to:
- Take numerical input from users.
- Convert input into numerical values.
- Perform arithmetic operations.
- Use a `while` loop for continuous input.
- Implement an accumulator.
- Handle invalid input.
- Validate numerical values.

**Project 3 – Random Password Generator**
I learned how to:
- Import Python's built-in modules.
- Use the `random` module.
- Use the `string` module.
- Generate random characters.
- Manipulate strings and lists.
- Create passwords based on user-defined length.
- Add numbers and special characters.
- Use `random.shuffle()` for additional randomization.

**Project 4 – General Knowledge Quiz**
I learned how to:
- Apply if-else logic to control program flow.
- Sanitize user input with `.strip()` and `.lower()`.
- Store structured data using a list of dictionaries.
- Use `enumerate()` to number questions during a loop.
- Maintain state with an integer accumulator across a loop.
- Format final output using f-strings.

## 💡 Skills Developed

Through these projects, I developed the following programming skills:
- Python fundamentals
- Problem solving
- Logical thinking
- Functions
- Lists
- Loops
- Conditional statements (if-else / control flow)
- User input handling
- Exception handling
- File handling
- JSON data storage
- Data persistence
- String manipulation
- String sanitization
- Module integration
- Random data generation
- Dictionaries and structured data

## 🧪 Testing

Each project was tested with different inputs to ensure that the programs behave correctly.

**Project 1**
- Adding tasks
- Viewing tasks
- Deleting tasks
- Empty task validation
- Invalid task numbers
- Saving and loading tasks

**Project 2**
- Multiple expenses
- Decimal expenses
- Zero expenses
- Invalid input
- Negative values
- Ending the program with `done`

**Project 3**
- Different password lengths
- Invalid length input
- Passwords containing letters
- Passwords containing numbers
- Passwords containing special characters
- Minimum password length validation

**Project 4**
- Correct answers with standard casing
- Correct answers with extra whitespace and mixed casing (sanitization check)
- Incorrect answers
- Score accumulation across multiple questions
- Final score display format

## 🎓 Conclusion

These four projects provided hands-on experience with Python programming and helped strengthen my understanding of how basic programming concepts can be applied to practical problems. The To-Do List project introduced lists, functions, and data persistence. The Expense Tracker project focused on numerical processing and accumulator logic. The Random Password Generator introduced Python library integration, randomization, and string manipulation. The General Knowledge Quiz introduced if-else control flow, input sanitization, and structured data with dictionaries.

Together, these projects helped build a stronger foundation in Python programming, problem-solving, data handling, and backend-oriented programming.

## 👨‍💻 Training Information
- **Program:** Python Programming Industrial Training
- **Organization:** DecodeLabs
- **Batch:** 2026
- **Projects Completed:** 4
- **Programming Language:** Python 3
- **Development Platform:** Google Colab / Python

## ⭐ Projects Completed
- ✅ Project 1 – To-Do List
- ✅ Project 2 – Expense Tracker
- ✅ Project 3 – Random Password Generator
- ✅ Project 4 – General Knowledge Quiz
