# Day 08: FLOOR, CEILING, MROUND, ABS, MOD, POWER and SQRT

## 1. The Idea: 50 / 3

`50 / 3 = 16.666...` It does not divide evenly. These three functions choose a clean multiple of 3:

| Function | What it does | Result for 50 and 3 |
|----------|--------------|---------------------|
| FLOOR | Goes **down** to the next multiple | 48 (48 / 3 = 16) |
| CEILING | Goes **up** to the next multiple | 51 (51 / 3 = 17) |
| MROUND | Picks the **nearest** multiple | 51 (51 is 1 away, 48 is 2 away) |

---

## 2. FLOOR, CEILING and MROUND

**Syntax:** `=FUNCTION(number, multiple)`. The second number is the multiple you want.

| Formula | Result |
|---------|--------|
| `=FLOOR(50,3)` | 48 |
| `=CEILING(50,3)` | 51 |
| `=MROUND(50,3)` | 51 |
| `=MROUND(49,3)` | 48 |

- The answer is always a **multiple** of the second number.
- `FLOOR.MATH` and `CEILING.MATH` also handle negative numbers.
- Cell reference version: `=FLOOR(K33,3)`.

---

## 3. ABS

Turns a negative value into a positive one.

| Formula | Result |
|---------|--------|
| `=ABS(-10)` | 10 |
| `=ABS(10)` | 10 |
| `=-ABS(10)` | -10 |
| `=ABS(A1-B1)` | The gap between two values |

A minus sign in front of ABS forces the answer to be negative. ABS is great for differences where the order does not matter.

---

## 4. MOD (Remainder)

| Formula | Result |
|---------|--------|
| `=MOD(10,3)` | 1 |
| `=MOD(9,3)` | 0 |
| `=MOD(7,2)` | 1 |
| `=QUOTIENT(10,3)` | 3 |

- 10 / 3 = 3 remainder **1**. MOD gives the remainder.
- **QUOTIENT** gives only the whole-number part.
- MOD = 0 means the number divides evenly.

### MOD in Real Life
- **Even or odd:** `=MOD(A1,2)=0` is TRUE for even numbers.
- **Every 3rd row:** `=MOD(ROW(),3)=0` (great with Conditional Formatting).
- **Multiple of 5?** `=MOD(A1,5)=0`
- **Time split:** `=QUOTIENT(135,60)` = 2 hours and `=MOD(135,60)` = 15 minutes.

---

## 5. POWER and SQRT

| Formula | Result |
|---------|--------|
| `=POWER(2,3)` | 8 |
| `=2^3` | 8 |
| `=POWER(5,2)` | 25 |
| `=SQRT(16)` | 4 |
| `=SQRT(50)` | 7.0710678 |

- 2 to the power 3 means 2 x 2 x 2 = **8** (not 6).
- `SQRT` of a negative number gives `#NUM!`. Use `=SQRT(ABS(x))` when the sign is unknown.

---

## 6. Combining Two Formulas (Nesting)

| Formula | Result |
|---------|--------|
| `=ROUND(SQRT(50),2)` | 7.07 |
| `=ROUND(SQRT(K33),2)` | Square root first, then rounded to 2 decimals |
| `=SQRT(ABS(-16))` | 4 |
| `=MOD(ABS(-10),3)` | 1 |
| `=ROUND(POWER(1.05,3),2)` | 1.16 |

**Rules**
- Excel solves the **innermost** function first, then works outward.
- Every function needs its own opening and closing bracket.
- The inner formula becomes one argument of the outer formula.

---

## 7. Shortcuts

| Shortcut | Action |
|----------|--------|
| Alt + M + V | Evaluate Formula (step through a formula) |
| F9 | Show the value of the selected part of a formula |
| Esc | Cancel and keep the original formula |
| F2 | Edit the formula |
| Ctrl + Shift + U | Expand the formula bar |
| Ctrl + ` | Show all formulas |
| Shift + F3 | Insert Function dialog |
| F4 | Lock a reference |

**Debug tip:** in the formula bar, select part of a formula, press F9 to see its result, then press **Esc** so the formula is not replaced by the value.

---

## 8. Interview Questions

- **FLOOR vs ROUNDDOWN?** FLOOR goes down to a **multiple** (3, 5, 10). ROUNDDOWN cuts to a number of **decimal places**.
- **MROUND vs ROUND?** ROUND uses decimal places. MROUND uses the nearest multiple.
- **How do you check even or odd?** `=MOD(A1,2)`: 0 means even, 1 means odd.
- **POWER vs `^`?** Same result. `2^3` and `POWER(2,3)` both give 8.

---

## 9. Cheat Sheet

| Group | Functions |
|-------|-----------|
| Multiples | FLOOR, CEILING, MROUND |
| Sign | ABS, SIGN |
| Division | MOD, QUOTIENT |
| Powers and roots | POWER, ^, SQRT |
| Rounding family | ROUND, ROUNDUP, ROUNDDOWN, INT, TRUNC |

---

## Key Takeaway

Use MOD for remainders and even/odd checks, and remember: formulas inside formulas are solved from the inside out.
