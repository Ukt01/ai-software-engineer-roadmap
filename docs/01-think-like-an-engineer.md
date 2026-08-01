# Stage 1: Think Like an Engineer

Welcome to Stage 1.

Before we write complex software, we need to adjust how we think about code. 

A developer writes code that computers can execute. A software engineer writes code that humans can easily read, maintain, and expand.

---

## 1. Clean Code & Meaningful Naming

Think of your code like labeling boxes in a storage room.

If you label a box `"Stuff"` or `"Box1"`, nobody knows what is inside without opening it. If you label it `"Winter Jackets 2026"`, everyone understands immediately.

### The Bad Way

```csharp
// What does x, d, or calc do?
var x = 86400;
var d = DateTime.Now;
public int calc(int a, int b) { return a * b; }
```

### The Engineer Way

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

## 3. SOLID Principles Made Simple

Do not be intimidated by acronyms. SOLID is just five practical habits for writing flexible code.

### S — Single Responsibility Principle

A class should have **one reason to change**.

- **Analogy:** A chef cooks meals. The chef should not also fix the restaurant plumbing or manage tax filings.
- **Code:** A `PaymentProcessor` class handles payments. It should not handle printing invoices to PDF.

### O — Open / Closed Principle

Code should be **open for extension, but closed for modification**.

- **Analogy:** Your smartphone lets you install new apps (extension) without taking the phone apart and rewiring the motherboard (modification).
- **Code:** Add new features by adding new classes, not by hacking existing working code.

### L — Liskov Substitution Principle

Child classes should work wherever parent classes are expected without breaking anything.

- **Analogy:** If you replace a standard battery with a rechargeable battery in a flashlight, the flashlight should still turn on normally.

### I — Interface Segregation Principle

Do not force a class to implement methods it does not need.

- **Analogy:** A simple printer should not be forced to have buttons for scanning, faxing, and stapling if it only prints paper.

### D — Dependency Inversion Principle

High-level modules should depend on abstractions (interfaces), not concrete implementations.

- **Analogy:** Your lamp plugs into a standard wall socket (interface). You don't hardwire your lamp directly into the power plant.

---

## 4. Error Handling & Logging

When things go wrong in production, you cannot open a debugger. You need clear logs.

### Friendly Error Handling Rules

1. Never catch errors and stay silent (avoid empty `catch` blocks).
2. Write error messages that explain **what happened** and **why**.
3. Log helpful details (e.g., `Failed to process payment for User #402: Invalid Card Expiry`).

---

## 5. Unit Testing Without Stress

A unit test is just a tiny automated script that checks if your function returns the expected result.

### The 3-Step Structure (AAA Pattern)

1. **Arrange:** Set up your test data.
2. **Act:** Call the function you want to test.
3. **Assert:** Check if the result matches what you expected.

### Example Concept

```csharp
// 1. Arrange
var calculator = new DiscountCalculator();

// 2. Act
var finalPrice = calculator.ApplyDiscount(total: 100, discountPercent: 10);

// 3. Assert
// Expected result is 90
```

---

## 💡 Stage 1 Practical Tasks & To-Do List

Complete these action items before moving to Stage 2:

- [ ] **Task 1:** Open an old project or script you wrote. Rename 5 vague variables (like `x`, `temp`, `data`) into clear, descriptive names.
- [ ] **Task 2:** Find a long function in your code (over 40 lines). Refactor it by splitting it into 2 or 3 smaller functions.
- [ ] **Task 3:** Pick one class in your app and check if it follows the Single Responsibility Principle. If it handles multiple unrelated tasks, separate them.
- [ ] **Task 4:** Add structured logging to an API endpoint or function so it logs when execution starts, succeeds, or fails.
- [ ] **Task 5:** Write your first basic unit test for a simple function (like calculating a discount or validating an email string).
