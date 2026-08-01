# Stage 1 — Week 2: SOLID Principles & Unit Testing

Welcome to Week 2 of Stage 1!

Now that you know how to write clean functions, let's look at how to structure classes and write basic automated tests.

---

## 1. SOLID Principles Made Simple

SOLID sounds complicated, but it is just 5 practical habits for building flexible software.

### S — Single Responsibility Principle

A class should have **one primary job**.

- **Analogy:** A chef cooks meals. The chef should not also fix restaurant plumbing or handle corporate tax filings.
- **Code:** A `PaymentProcessor` class handles payments. It should not handle printing invoices to PDF files.

---

### O — Open / Closed Principle

Code should be **open for extension, but closed for modification**.

- **Analogy:** Your smartphone lets you install new apps (extension) without taking the phone apart and rewiring the hardware (modification).
- **Code:** Add new features by adding new classes, not by hacking existing working code.

---

### L — Liskov Substitution Principle

Child classes should work wherever parent classes are expected without breaking anything.

- **Analogy:** If you replace a standard battery with a rechargeable battery in a flashlight, the flashlight should still turn on normally.

---

### I — Interface Segregation Principle

Do not force a class to implement methods it does not need.

- **Analogy:** A basic printer should not have forced buttons for scanning, faxing, and stapling if it only prints paper.

---

### D — Dependency Inversion Principle

High-level modules should depend on abstractions (interfaces), not concrete implementations.

- **Analogy:** Your lamp plugs into a standard wall socket (interface). You don't hardwire your lamp directly into the power grid.

---

## 2. Unit Testing Without Stress

A unit test is just a tiny automated script that checks if your function returns the expected result.

### The AAA Pattern (3 Simple Steps)

1. **Arrange:** Set up your test data.
2. **Act:** Call the function you want to test.
3. **Assert:** Check if the result matches what you expected.

### Simple Example Concept

```csharp
// 1. Arrange
var calculator = new DiscountCalculator();

// 2. Act
var finalPrice = calculator.ApplyDiscount(totalPrice: 100, discountPercent: 10);

// 3. Assert
// Check that finalPrice equals 90
```

---

## 💡 Week 2 To-Do List & Tasks

Complete these hands-on steps before moving to Stage 2:

- [ ] **Task 1:** Pick one class in your app. Check if it handles multiple unrelated jobs. Split it so each class has one clear responsibility.
- [ ] **Task 2:** Create a simple interface for a service (like `IEmailService` or `IPaymentGateway`).
- [ ] **Task 3:** Write your first unit test following the Arrange-Act-Assert pattern for a calculator or validation function.
