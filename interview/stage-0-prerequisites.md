# Stage 0 Interview Questions & Answers — Prerequisites

A curated set of technical interview questions, conceptual checks, and model answers covering Object-Oriented Programming (OOP), SQL, REST APIs, Git, and systematic debugging.

---

## 1. Object-Oriented Programming (OOP)

### Q1: What is the fundamental difference between a Class and an Object?
**Model Answer:**
- A **Class** is an abstract blueprint or template that defines properties (data) and methods (behavior). It consumes no runtime object memory until instantiated.
- An **Object** is a concrete instance of a class allocated on the heap during runtime. Multiple distinct objects can be created from a single class blueprint, each holding its own independent state.

### Q2: What is Encapsulation and why is it important in software development?
**Model Answer:**
Encapsulation is the OOP principle of bundling data (fields) and methods operating on that data within a single class while restricting direct external access to internal state (e.g., using `private` or `protected` modifiers). 
**Why it matters:**
1. **Data Integrity:** Prevents outside code from corrupting internal state.
2. **Maintainability:** Allows changing internal implementation details without breaking external consumers.

---

## 2. SQL & Relational Databases

### Q3: What is the difference between `WHERE` and `HAVING` clauses in SQL?
**Model Answer:**
- `WHERE` filters individual rows **before** grouping or aggregation occurs. It cannot contain aggregate functions like `SUM()` or `COUNT()`.
- `HAVING` filters aggregated group records **after** the `GROUP BY` clause is evaluated.

**Example Query:**
```sql
SELECT Department, COUNT(EmployeeId) AS TotalStaff
FROM Employees
WHERE Status = 'Active'         -- Filters rows first
GROUP BY Department
HAVING COUNT(EmployeeId) > 5;   -- Filters aggregated groups
```

### Q4: Explain the difference between `INNER JOIN` and `LEFT JOIN`.
**Model Answer:**
- `INNER JOIN`: Returns only the matching rows where join conditions evaluate to true in **both** left and right tables. Unmatched rows from either table are excluded.
- `LEFT JOIN` (or `LEFT OUTER JOIN`): Returns **all** rows from the left table regardless of matches, along with matching rows from the right table. Non-matching right table columns return `NULL`.

---

## 3. REST APIs & HTTP Communications

### Q5: What makes an HTTP method "Idempotent"? Give examples.
**Model Answer:**
An HTTP method is **idempotent** if making multiple identical requests produces the exact same server side effect as making a single request.
- **Idempotent Methods:** `GET`, `PUT`, `DELETE`. (Executing `DELETE /api/users/42` ten times yields the same result: User 42 is removed).
- **Non-Idempotent Methods:** `POST`. (Executing `POST /api/orders` ten times creates 10 separate duplicate order records).

### Q6: Explain the difference between HTTP Status Codes `401 Unauthorized` and `403 Forbidden`.
**Model Answer:**
- `401 Unauthorized`: Indicates **lack of valid authentication credentials**. The client must authenticate (provide valid token or credentials) before retrying.
- `403 Forbidden`: Indicates the client **is authenticated**, but lacks sufficient authorization/permissions to access the requested resource. Re-authenticating with identical credentials will fail.

---

## 4. Git & Version Control

### Q7: What is the difference between `git fetch` and `git pull`?
**Model Answer:**
- `git fetch`: Downloads new commits, tags, and refs from the remote repository into local memory, but **does not alter or merge** into your working directory code.
- `git pull`: Performs a `git fetch` immediately followed by a `git merge` (or `git rebase`), automatically updating your active working branch with remote changes.

### Q8: What are staged vs unstaged changes in Git?
**Model Answer:**
- **Unstaged Changes:** Edits made to tracked files in your working directory that have not yet been marked for commit.
- **Staged Changes:** Edits added to the Git Index (via `git add`). Only staged changes will be captured in the next `git commit` execution.

---

## 5. Debugging & Error Handling

### Q9: How do you approach debugging a `NullReferenceException` (or `TypeError: Cannot read property of undefined`)?
**Model Answer:**
1. **Read Stack Trace:** Locate the exact line number and file in application code where exception was thrown.
2. **Identify Target Object:** Pinpoint which specific object reference on that line was evaluated as `null`.
3. **Trace Variable Initialization:** Move backwards step-by-step to see where the variable was assigned or initialized.
4. **Enforce Guard Clause / Null Check:** Validate inputs or add fallback logic before dereferencing object properties:
   ```csharp
   // Defensive guard clause
   if (user == null) throw new ArgumentNullException(nameof(user));
   ```

---

## 6. Interview Quick Knowledge Check Matrix

| Topic | Key Question | Flashcard Concept |
| :--- | :--- | :--- |
| **OOP** | Difference between `interface` & `abstract class` | Interface = Contract; Abstract class = Base code + contract |
| **SQL** | Primary Key vs Foreign Key | PK = Unique row ID; FK = Reference to PK in another table |
| **REST** | `PUT` vs `PATCH` | PUT = Full entity replacement; PATCH = Partial field update |
| **Git** | `git reset` vs `git revert` | Reset rewrites local history; Revert creates new commit undoing changes |
| **Debug** | Breakpoint vs Console Log | Breakpoint pauses execution interactively; Log records history without pause |
