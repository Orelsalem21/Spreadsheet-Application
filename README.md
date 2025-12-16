# Spreadsheet-Application
Java-based Spreadsheet Engine featuring a custom recursive formula parser, boolean logic support, cycle detection algorithms, and GUI. Includes comprehensive JUnit testing.

# Java Spreadsheet Engine

![Java](https://img.shields.io/badge/Language-Java-orange)
![Testing](https://img.shields.io/badge/Testing-JUnit-green)
![Build](https://img.shields.io/badge/Build-Passing-brightgreen)

> A robust, object-oriented spreadsheet application featuring a custom recursive formula parser, boolean logic support, and algorithmic cycle detection.

## 📖 Overview
This project is a fully functional **Spreadsheet Engine** built from scratch in Java. Unlike standard grid components, this application implements a custom **Recursive Descent Parser** to evaluate complex mathematical expressions and nested logical conditions.

The system is designed with a focus on data integrity, utilizing dependency graphs to detect **Circular References** (preventing stack overflow errors) and comprehensive error handling for invalid formulas.

### Key Technical Features
* **Custom Parser:** Evaluates arithmetic operators (`+`, `-`, `*`, `/`) and respects standard order of operations (parentheses).
* **Boolean Logic:** Supports nested `IF` statements and comparison operators (`<`, `>`, `!=`).
* **Range Aggregation:** Efficient calculation of 2D range functions (`SUM`, `MIN`, `MAX`, `AVERAGE`).
* **Cycle Detection:** Algorithmic identification of circular dependencies (e.g., A1 references B1, B1 references A1).
* **Persistence:** Save and Load functionality to preserve spreadsheet state (CSV/Text format).
* **GUI:** Interactive graphical interface built with Swing/AWT principles.

---

## 📸 Demo

![Application Screenshot](spreadsheet_screenshot.png)

*(Note: The interface supports dynamic cell resizing and real-time updates)*

---

## 🎨 UI & Legend
The interface provides immediate visual feedback based on cell state:

| Color | Type | Description |
| :--- | :--- | :--- |
| **Black** | Text/Number | Plain static values. |
| **Blue** | Formula | Calculated fields starting with `=`. |
| **Pink** | Function | Range functions (`MIN`, `MAX`, `AVG`, `SUM`). |
| **Yellow** | Logic | `IF` expressions. |
| **Red** | Error | General format or syntax errors. |
| **Dark Red** | Critical | **Circular Reference** (Cycle detected). |

---

## ⚡ Features & Usage Examples

### 1. Range Functions
Perform operations on 2D grids of cells:
```text
=sum(A1:C5)       → Sum of all values in the range
=min(B2:D4)       → Finds the minimum value
=max(C1:D3)       → Finds the maximum value
=average(A1:B2)   → Calculates the average

### 2. Advanced Conditional Logic
Supports nesting for complex decision trees:
=if(A1>10, "High", "Low")
=if(A1>10, if(B1<5, 50, "Check"), "Low")  // Nested IF
=if(A1*A2 != A3/(2-A1), A2+2, A1+1)       // Formulas inside conditions

### 3. Error Handling Protocols
The engine identifies and categorizes errors to assist debugging:
Error Tag,Meaning
ERR_CYCLE,Circular Reference: A cell refers to itself directly or indirectly.
IF_ERR,Logic Error: Invalid format in an IF statement.
FUNC_ERR,Syntax Error: Invalid function name or malformed range.
ERR_FORM,Formula Error: General parsing failure.

### Quality Assurance (Testing)
As a project emphasizing reliability, the codebase is covered by a comprehensive JUnit test suite targeting:
Parser Logic: Validating operator precedence and recursion depth.
Edge Cases: Testing empty ranges, division by zero, and negative values.
Logic Gates: Verifying deep nesting of IF conditions.
Dependency Graph: Ensuring ERR_CYCLE is triggered correctly for circular loops.
Data Propagation: Verifying that updating one cell correctly updates all dependent cells.

###

Author
Orel Salem
Computer Science Student & QA Specialist
