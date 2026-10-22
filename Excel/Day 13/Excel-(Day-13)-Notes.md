# Day 13: Day 1-12 Revision (Shortcuts and Formulas)

## 1. Your 12-Day Map

| Days | Topics |
|------|--------|
| Day 1-2 | Excel basics, shortcuts, formatting, formulas, Paste Special, Conditional Formatting |
| Day 3-4 | Clipboard, Filter, Sort, Tables, Fill Series, Go To Special, cell references |
| Day 5-6 | RANK, text formulas, first recap |
| Day 7-8 | Random numbers, rounding, FLOOR, CEILING, MOD, POWER, SQRT |
| Day 9-10 | Date and time formulas, logical formulas (IF, AND, OR, IFS) |
| Day 11-12 | SUMIF family, attendance tracker, SUMIFS, Excel errors |

---

## 2. Shortcuts

### Navigation and Selection
| Shortcut | Action |
|----------|--------|
| Ctrl + Home | First cell (A1) |
| Ctrl + End | Last used cell |
| Ctrl + Arrow | Jump to the edge of data |
| Ctrl + Shift + Arrow | Select to the end of data |
| Ctrl + A | Select all data |
| Ctrl + G (or F5) | Go To |
| Ctrl + PgDn / PgUp | Next / previous sheet |
| Ctrl + Space | Select entire column |
| Shift + Space | Select entire row |

### Format and Number
| Shortcut | Action |
|----------|--------|
| Ctrl + 1 | Format Cells box |
| Ctrl + B / I / U | Bold / Italic / Underline |
| Alt + H + O + I | AutoFit column width |
| Alt + H + A + C | Center align |
| Alt + H + W | Wrap text |
| Alt + H + B + A | All borders |
| Ctrl + Shift + ! | Number format |
| Ctrl + Shift + $ | Currency |
| Ctrl + Shift + % | Percentage |
| Ctrl + Shift + # | Date format |

### Data Tools
| Shortcut | Action |
|----------|--------|
| Ctrl + Shift + L | Filter on / off |
| Alt + Down | Open filter dropdown |
| Alt + A + S + A | Sort A to Z |
| Ctrl + T | Create Excel Table |
| Ctrl + E | Flash Fill |
| Alt + A + E | Text to Columns |
| Alt + = | AutoSum |
| Alt + H + F + I + S | Fill Series |

### Formula Shortcuts
| Shortcut | Action |
|----------|--------|
| F4 | Lock a reference ($) |
| Tab | Accept the function name |
| Ctrl + A | Function Arguments box (after typing the function name) |
| Shift + F3 | Insert Function box |
| F9 | Recalculate / show the value of a selected part |
| Alt + M + V | Evaluate Formula |
| Ctrl + ` | Show all formulas |
| Alt + Enter | Line break inside a formula |

### Go To and Clean-Up
| Shortcut | Action |
|----------|--------|
| Ctrl + G, then Special | Go To Special |
| Alt + ; | Select visible cells only |
| Ctrl + Shift + * | Current region |
| Ctrl + \\ | Row differences |
| Ctrl + [ / Ctrl + ] | Select precedent / dependent cells |
| Alt + H + E + A | Clear all |
| Ctrl + Enter | Fill all selected cells |

### Edit, Date and Paste
| Shortcut | Action |
|----------|--------|
| Ctrl + ; | Today's date (fixed) |
| Ctrl + Shift + ; | Current time (fixed) |
| Ctrl + Alt + V, then V | Paste values only |
| Ctrl + Alt + V, then E | Transpose |
| Ctrl + Alt + V, then D / S / M / I | Add / Subtract / Multiply / Divide |
| Ctrl + D / Ctrl + R | Fill down / right |
| Ctrl + Z / Ctrl + Y | Undo / Redo |
| Ctrl + F / Ctrl + H | Find / Replace |
| F2 | Edit the cell |

Key tips (Alt + letters) can vary by Excel version. Press Alt to check.

---

## 3. Math and Rounding (Day 7-8)

| Formula | Result |
|---------|--------|
| `=ROUND(5.678,1)` | 5.7 |
| `=ROUNDUP(5.612,1)` | 5.7 |
| `=ROUNDDOWN(5.678,1)` | 5.6 |
| `=INT(-5.5)` | -6 |
| `=TRUNC(-5.5)` | -5 |
| `=FLOOR(50,3)` | 48 |
| `=CEILING(50,3)` | 51 |
| `=MROUND(50,3)` | 51 |
| `=ABS(-10)` | 10 |
| `=MOD(10,3)` | 1 |
| `=POWER(2,3)` | 8 |
| `=SQRT(16)` | 4 |
| `=RANDBETWEEN(1,100)` | Random whole number (F9 recalculates) |

---

## 4. Statistics and Ranking (Day 2, 5, 7)

| Formula | Result |
|---------|--------|
| `=SUM(A2:A4)` | Add a range |
| `=AVERAGE(A2:A4)` | Average |
| `=MAX(A2:A4)` / `=MIN(A2:A4)` | Largest / smallest |
| `=LARGE(B2:B11,2)` | 2nd largest |
| `=SMALL(B2:B11,2)` | 2nd smallest |
| `=RANK(F5,$F$5:$F$19)` | Position (lock the list with $) |
| `=COUNT(...)` / `=COUNTA(...)` / `=COUNTBLANK(...)` | Numbers / non-empty / empty cells |

---

## 5. Text Formulas (Day 5)

A1 = `Mr. Oneeb Arif`

| Formula | Result |
|---------|--------|
| `=LEFT(A1,3)` | Mr. |
| `=RIGHT(A1,4)` | Arif |
| `=MID(A1,5,5)` | Oneeb |
| `=LEN("Oneeb")` | 5 |
| `=TRIM(" Hello ")` | Hello |
| `=PROPER("oneeb arif")` | Oneeb Arif |
| `=TEXTJOIN(" ",TRUE,B1,C1)` | Joins with a space |
| `=SUBSTITUTE(B77,"-","@")` | AXP@7842@MNO |
| `=REPLACE(H77,5,4,2026)` | AXP-2026-MNO |
| `=FIND("A","EIM-4532-ABC")` | 10 |
| `=TEXTSPLIT(A1," ")` | Splits into cells (Microsoft 365) |

---

## 6. Date and Time (Day 9)

D1 = `18-Oct-2026`. A1 = date of birth `04-11-2004`, B1 = today `18-10-2026`.

| Formula | Result |
|---------|--------|
| `=TODAY()` | Live date |
| `=NOW()+7/24` | 7 hours from now |
| `=DATEDIF(A1,B1,"Y")` | 21 (age in years) |
| `=NETWORKDAYS(C1,D1)` | Working days between two dates (skips Sat and Sun) |
| `=WORKDAY(D1,7)` | 27-Oct-2026 |
| `=EDATE(D1,2)` | 18-Dec-2026 |
| `=EOMONTH(D1,0)` | 31-Oct-2026 |
| `=WEEKDAY(D1)` | 1 (Sunday) |
| `=TEXT(D1,"dddd")` | Sunday |

---

## 7. Logical Formulas (Day 10)

| Formula | Meaning |
|---------|---------|
| `=IF(B2>=33%,"Pass","Fail")` | Pass or Fail |
| `=AND(D24>=50000,E24>=3)` | Both conditions must be TRUE |
| `=OR(D24>=50000,E24>=3)` | Any one condition is enough |
| `=IFS(K4>=90%,"A",TRUE,"F")` | Many conditions (TRUE catches the rest) |
| `=SWITCH(A1,"A+",5000,0)` | Exact match |
| `=IFERROR(A1/B1,0)` | Hide the error |
| `=ISBLANK(C33)` | TRUE if the cell is empty |

---

## 8. Conditional Totals (Day 11-12)

| Formula | Meaning |
|---------|---------|
| `=SUMIF(B:B,F2,C:C)` | Total for one party |
| `=AVERAGEIF(B:B,F2,C:C)` | Average for one party |
| `=COUNTIF(B:B,F2)` | How many times the party appears |
| `=SUMIFS(C:C,B:B,$A3,D:D,B$2)` | Sum with 2 conditions |
| `=COUNTIFS(B:B,$A3,D:D,B$2)` | Count with 2 conditions |
| `=MAXIFS(C:C,B:B,F2)` | Biggest value for party F2 |

---

## 9. Common Mix-Ups

- **SUMIF vs SUMIFS:** SUMIF is `range, criteria, sum_range`. In SUMIFS the **sum range comes first**.
- **FIND vs SEARCH:** FIND is case-sensitive. SEARCH is not.
- **INT vs TRUNC:** same for positives. `INT(-5.5) = -6`, `TRUNC(-5.5) = -5`.
- **`NOW()+7`:** adds 7 **days**. Use `NOW()+7/24` for 7 hours.
- **Format vs ROUND:** the decimal buttons change the look. ROUND changes the real value.

---

## 10. Excel Errors

| Error | Meaning |
|-------|---------|
| `#DIV/0!` | Divided by 0 or a blank cell |
| `#VALUE!` | Wrong data type |
| `#NAME?` | Wrong function name |
| `#REF!` | Deleted cell reference |
| `#N/A` | Value not available |
| `#NUM!` | Invalid numerical calculation |
| `#NULL!` | Wrong range intersection |
| `#SPILL!` | Spill range is blocked |
| `#####` | Column too narrow |

---

## 11. Golden Rules

- **Lock with F4:** `A1` moves, `$A$1` never moves, `$A1` locks the column, `A$1` locks the row.
- **Quotes:** text goes in `"quotes"`. Numbers and cell references do not.
- **Nested formulas:** Excel solves from the inside out. Use one closing bracket per function.
- **Dates:** dates are serial numbers. Format the cell as a date to read them.
- **Tables:** Ctrl + T makes data grow, format and calculate automatically.

---

## 12. Practice Challenge

Try these without looking at your notes:

1. Total sales of one party with **SUMIF**.
2. Build a **Supplier x Month** report with **SUMIFS**.
3. Grade marks with **IFS** and rank them with **RANK**.
4. Calculate age with **DATEDIF** and a due date with **EDATE**.
5. Clean a name list with **TRIM** and **PROPER**, then split it with **TEXTSPLIT** or **Flash Fill**.

---

## Key Takeaway

Revision turns notes into skill. Practise the five tasks above until you can do them without help.
