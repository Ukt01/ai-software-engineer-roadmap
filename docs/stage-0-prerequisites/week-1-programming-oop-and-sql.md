# Stage 0 — Week 1: Programming Foundations, OOP & SQL

Welcome to Stage 0, Week 1!

Before we architect high-level AI systems, we need a solid grip on basic programming building blocks: how code flows, how object-oriented programming organizes data, and how databases store information.

---

## 1. Programming Foundations

Every programming language (C#, Python, JavaScript, Java) shares the exact same core building blocks:

- **Variables:** Containers that hold information (strings, numbers, booleans).
- **Conditions:** Decision branches (`if / else`) that control which code executes.
- **Loops:** Repeating an action until a condition is met (`foreach`, `while`).

### Real-World Analogy

Think of a cooking recipe:
- Variables are your ingredients.
- Conditions check if the oven is preheated.
- Loops stir the soup until it boils.

---

## 2. Object-Oriented Programming (OOP)

OOP is simply a way to group related data and actions together so your code mirrors the real world.

### The Blueprint & House Analogy

- **Class:** The architectural blueprint of a house. It defines rooms, doors, and color.
- **Object:** The actual physical house built using that blueprint. You can build 50 houses from 1 blueprint.
- **Properties:** Characteristics of the house (e.g., `NumberOfBedrooms = 3`).
- **Methods:** Actions the house can perform (e.g., `LockFrontDoor()`).

### Simple Example Concept

```csharp
public class Car
{
    public string Model { get; set; }
    public int Speed { get; set; }

    public void Accelerate()
    {
        Speed += 10;
    }
}
```

---

## 3. Basic SQL & Databases

A relational database is like a digital filing cabinet made of tables with rows and columns.

### The 4 Core Operations (CRUD)

1. **CREATE (INSERT):** Add a new record.
   ```sql
   INSERT INTO Users (Name, Email) VALUES ('Alice', 'alice@example.com');
   ```

2. **READ (SELECT):** Retrieve existing records.
   ```sql
   SELECT * FROM Users WHERE Email = 'alice@example.com';
   ```

3. **UPDATE:** Modify an existing record.
   ```sql
   UPDATE Users SET Name = 'Alice Smith' WHERE Email = 'alice@example.com';
   ```

4. **DELETE:** Remove a record.
   ```sql
   DELETE FROM Users WHERE Email = 'alice@example.com';
   ```

---

## 💡 Week 1 To-Do List & Tasks

Complete these hands-on steps before moving to Week 2:

- [X] **Task 1:** Create a simple class (`User` or `Product`) with 3 properties and 1 method in your preferred language.
- [X] **Task 2:** Instantiate 2 separate objects from your class and call its method.
- [X] **Task 3:** Write and run basic SQL queries (`SELECT`, `INSERT`, `UPDATE`, `DELETE`) on a local database (SQLite, SQL Server, or PostgreSQL).
