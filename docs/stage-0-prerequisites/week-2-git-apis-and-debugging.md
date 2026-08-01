# Stage 0 — Week 2: REST APIs, Git & Debugging

Welcome to Stage 0, Week 2!

Now that you understand variables, objects, and databases, this week focuses on how applications communicate with each other over the internet, how to save your code history with Git, and how to debug errors.

---

## 1. REST APIs & HTTP Basics

An API (Application Programming Interface) allows two different software applications to talk to each other over the web.

### The Restaurant Analogy

- **Client (You / Browser):** Sits at the table and looks at the menu.
- **Server (Backend / Database):** The kitchen preparing the food.
- **API (The Waiter):** Takes your request to the kitchen and brings back your order.

### The 4 Standard HTTP Verbs

- **GET:** Fetch data (e.g., Get list of products).
- **POST:** Submit new data (e.g., Create a new user account).
- **PUT:** Replace existing data (e.g., Update full user profile).
- **DELETE:** Remove data (e.g., Delete an order).

Data is transferred using **JSON** (JavaScript Object Notation):

```json
{
  "userId": 101,
  "name": "Udit Thakur",
  "role": "Developer"
}
```

---

## 2. Essential Git Commands

Git is your time-travel machine for code. It records changes so you can revert mistakes or work with teammates.

### The Video Game Save Point Analogy

- `git status` — Check which items in your inventory have changed.
- `git add .` — Pack changes into your save file.
- `git commit -m "Message"` — Create the save point with a description.
- `git push` — Upload your save file to the cloud (GitHub).

### Basic Command Sequence

```bash
# Check current state
git status

# Stage all updated files
git add .

# Commit with a clear message
git commit -m "feat: add user login endpoint"

# Push to remote repository
git push origin main
```

---

## 3. How to Debug Errors Like a Developer

When code crashes, do not panic. Error messages (stack traces) tell you exactly **where** and **why** something failed.

### Simple Debugging Steps

1. **Read the Stack Trace:** Look at the bottom lines first—they show the exact line number where the error occurred.
2. **Check Your Inputs:** Verify that variables are not `null` or `undefined` before using them.
3. **Use Console / Log Statements:** Print variable values right before the crash line to inspect their actual contents.
4. **Use Breakpoints:** Pause execution step-by-step using your IDE debugger (Visual Studio / VS Code).

---

## 💡 Week 2 To-Do List & Tasks

Complete these hands-on steps before moving to Stage 1:

- [ ] **Task 1:** Make a GET request to a public API (like `https://jsonplaceholder.typicode.com/todos/1`) using Postman or your browser.
- [ ] **Task 2:** Initialize a local Git repository, make 2 commits, and push your code to a public GitHub repository.
- [ ] **Task 3:** Intentionally cause a null reference / undefined error in your code, read the stack trace, and use a log statement or debugger breakpoint to fix it.
