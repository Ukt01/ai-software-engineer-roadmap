# Stage 1 — Week 1: Clean Code & Meaningful Naming

Welcome to Week 1 of Stage 1!

Before writing complex applications, we must master writing clean, readable code. 

A computer understands any code. A great software engineer writes code that human teammates can read and maintain without headache.

---

## 1. Meaningful Naming

Think of your code like labeling boxes in a storage room.

If you label a box `"Stuff"` or `"Box1"`, nobody knows what is inside without opening it. If you label it `"Winter Jackets 2026"`, everyone understands immediately.

### Bad Example

```csharp
// What does x, d, or calc do?
var x = 86400;
var d = DateTime.Now;
public int calc(int a, int b) { return a * b; }
```

### Engineer Example

```csharp
var secondsInOneDay = 86400;
var currentTimestamp = DateTime.Now;
public int CalculateTotalOrderPrice(int unitPrice, int quantity) { return unitPrice * quantity; }
```

### Why This Matters

You read code 10 times more often than you write code. Clear names save hours of confusion for you and your team later.

---

## 2. Write Small Functions

Imagine reading a book with no paragraphs, chapters, or periods—just one giant wall of text. It would be exhausting.

Functions in code are like paragraphs. One function should do **one thing well**.

### Real-World Analogy: Preparing Coffee

A good coffee routine breaks down into distinct steps:
1. Grind beans
2. Boil water
3. Brew coffee

If one function handles brewing coffee, charging your credit card, and emailing your receipt, it becomes impossible to fix when something breaks.

### The Rule

Keep functions short (ideally under 20-30 lines). If a function is doing multiple tasks, break it into smaller helper functions.

---

## 3. Friendly Error Handling & Logging

When things break in production, you cannot attach a live debugger. You need clear logs.

### Friendly Rules

1. Never catch errors silently (avoid empty `catch` blocks).
2. Write error messages that explain **what happened** and **why**.
3. Log helpful details (e.g., `Failed to process payment for User #402: Invalid Card Expiry`).

---

## 💡 Week 1 To-Do List & Tasks

Complete these hands-on steps before moving to Week 2:

- [ ] **Task 1:** Open an old project or script you wrote. Rename 5 vague variables (like `x`, `temp`, `data`) into clear, descriptive names.
- [ ] **Task 2:** Find a long function in your code (over 40 lines). Break it into 2 or 3 smaller helper functions.
- [ ] **Task 3:** Add clear error logging to one function so it records when execution starts, succeeds, or fails.
