# Day 06: Day 1-5 Recap, Shortcuts and Interview Prep

A one-page revision of everything from Day 1 to Day 5.

## 1. Navigation and Selection

| Shortcut | Action |
|----------|--------|
| Ctrl + Home | First cell (A1) |
| Ctrl + End | Last used cell |
| Ctrl + Arrow | Jump to the edge of data |
| Ctrl + Shift + Arrow | Select to the end of data |
| Ctrl + A | Select all data |
| Shift + Arrow | Select cell by cell |
| Ctrl + Space | Select entire column |
| Shift + Space | Select entire row |
| Ctrl + G (or F5) | Go To |
| Ctrl + PgDn / PgUp | Next / previous sheet |
| Ctrl + Tab | Next workbook |
| Tab / Shift + Tab | Move right / left |
| Enter / Shift + Enter | Move down / up |
| Ctrl + Click | Select multiple cells |

---

## 2. Edit and Fill

| Shortcut | Action |
|----------|--------|
| F2 | Edit the cell |
| Ctrl + Z / Ctrl + Y | Undo / Redo |
| Ctrl + D | Fill down |
| Ctrl + R | Fill right |
| Alt + H + F + I + U | Fill up |
| Alt + H + F + I + L | Fill left |
| Alt + H + F + I + S | Fill Series dialog |
| Ctrl + Enter | Fill all selected cells |
| Alt + Enter | New line inside a cell |
| Ctrl + ; | Insert today's date |
| Ctrl + Shift + ; | Insert current time |
| Ctrl + Shift + + | Insert row / column / cells |
| Ctrl + - | Delete row / column / cells |

---

## 3. Format Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl + B / I / U | Bold / Italic / Underline |
| Ctrl + 5 | Strikethrough |
| Ctrl + 1 | Format Cells box |
| Alt + H + F + F | Font style |
| Alt + H + F + S | Font size |
| Alt + H + O + I | AutoFit column width |
| Alt + H + O + A | AutoFit row height |
| Alt + H + A + C | Center align |
| Alt + H + A + M | Middle align |
| Alt + H + A + T / B | Top / Bottom align |
| Alt + H + 6 / 5 | Increase / decrease indent |
| Alt + H + W | Wrap text |
| Alt + H + M + C | Merge & Center |
| Alt + H + M + U | Unmerge |
| Alt + H + B + A | All borders |
| Alt + H + B + T | Thick outside border |
| Alt + H + B + N | No border |
| Alt + H + H | Cell (fill) color |
| Alt + H + F + C | Font color |
| Alt + H + F + P | Format Painter |
| Alt + H + H + N | Clear cell color |

---

## 4. Number Format Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl + Shift + ! | Number (1,000.00) |
| Ctrl + Shift + $ | Currency |
| Ctrl + Shift + % | Percentage |
| Ctrl + Shift + # | Date |
| Ctrl + Shift + @ | Time |
| Ctrl + Shift + ~ | General |
| Alt + H + 0 | Increase decimal |
| Alt + H + 9 | Decrease decimal |

---

## 5. Data Tools

| Shortcut | Action |
|----------|--------|
| Ctrl + Shift + L | Filter on / off |
| Alt + Down | Open filter dropdown |
| Alt + A + C | Clear filter |
| Ctrl + Alt + L | Reapply filter |
| Alt + A + S + A | Sort A to Z |
| Alt + A + S + D | Sort Z to A |
| Alt + A + S + S | Custom Sort |
| Ctrl + T | Create Excel Table |
| Ctrl + Shift + T | Table Total Row |
| Alt + J + T + G | Convert table to range |
| Alt + A + E | Text to Columns |
| Ctrl + E | Flash Fill |
| Alt + = | AutoSum |

Key tips can vary by Excel version. Press Alt to check.

---

## 6. Copy, Paste and Find

| Shortcut | Action |
|----------|--------|
| Ctrl + C / X / V | Copy / Cut / Paste |
| Win + V | Windows clipboard history |
| Ctrl + Alt + V | Paste Special |
| Ctrl + Alt + V, then V | Values only |
| Ctrl + Alt + V, then F | Formulas only |
| Ctrl + Alt + V, then T | Formats only |
| Ctrl + Alt + V, then E | Transpose |
| Ctrl + Alt + V, then L | Paste Link |
| Ctrl + Alt + V, then B | Skip blanks |
| Ctrl + Alt + V, then D / S / M / I | Add / Subtract / Multiply / Divide |
| Ctrl + Alt + V, then W | Column widths |
| Alt + ; | Select visible cells only |
| Ctrl + F | Find |
| Ctrl + H | Find and Replace |
| F4 | Lock reference ($A$1) |

---

## 7. Audit and Clear

| Shortcut | Action |
|----------|--------|
| Ctrl + Shift + * | Select current region |
| Ctrl + \\ | Row differences |
| Ctrl + Shift + \| | Column differences |
| Ctrl + [ | Select precedent cells |
| Ctrl + ] | Select dependent cells |
| Alt + M + P | Trace Precedents |
| Alt + M + D | Trace Dependents |
| Alt + M + A | Remove arrows |
| Ctrl + ` | Show / hide all formulas |
| Alt + H + E + A | Clear all |
| Alt + H + E + F | Clear formatting |
| Alt + H + E + C | Clear contents |

---

## 8. Interview Questions and Answers

### Basics
- **Formula vs Function?** A formula is written by you (`=A1+B1`). A function is predefined (`=SUM(A1:A5)`).
- **Excel limits?** 1,048,576 rows and 16,384 columns (A to XFD).
- **Workbook vs worksheet?** The workbook is the whole file. Worksheets are the pages inside it.
- **Constant vs formula?** Click the cell. A typed value in the Formula Bar is a constant. Something starting with `=` is a formula.

### Cell References
- **Reference types?** `A1` is relative (moves when copied), `$A$1` is absolute (never moves), `$A1` locks the column, `A$1` locks the row.
- **How do you lock a cell?** Press **F4** on the reference (Fn + F4 on many laptops). It cycles `$A$1` > `A$1` > `$A1` > `A1`.
- **Why not hardcode numbers?** `=A1+B1` updates by itself. `=100+200` never changes.
- **Classic use of $?** `=G5/$F$1` divides every row by one fixed total.

### Functions
- **COUNT vs COUNTA vs COUNTBLANK?** Numbers only, all non-empty cells, empty cells only.
- **`SUM(A1,A3)` vs `SUM(A1:A3)`?** The first adds only A1 and A3. The second adds A1, A2 and A3.
- **How does RANK treat ties?** Tied values share a rank and the next rank is skipped (9, 9, 11). Lock the list with `$`.
- **PRODUCT vs `*`?** Same answer. PRODUCT accepts a whole range.

### Tables, Filter, Sort and Conditional Formatting
| Feature | Normal range | Excel Table |
|---------|--------------|-------------|
| Growth | Fixed range | Auto-expands |
| Formulas | Not dynamic | Dynamic |
| Filtering | Filter only | Filter + Slicer |
| References | A1:A10 | Structured `[@Salary]` |
| Totals | Manual AutoSum | Total Row |
| Merged cells | Allowed | Not allowed |

- **Filter vs Conditional Formatting?** Filter hides other data. Conditional Formatting shows everything and only highlights.
- **What is a Slicer?** A button-style filter for Tables, easier than the dropdown.
- **Sort by many levels?** Custom Sort (e.g. Department first, then Sales largest to smallest).
- **Conditional Formatting types?** Highlight Cells Rules, Top/Bottom Rules, Data Bars, Color Scales, Icon Sets.

### Paste Special
- **Formulas to values?** Ctrl + C > Ctrl + Alt + V > V > Enter.
- **Add 1000 to a whole column?** Copy 1000 > select the column > Paste Special > Add.
- **Skip Blanks vs Paste Link?** Skip Blanks keeps existing data in the destination. Paste Link updates when the source changes.
- **Transpose?** Turns rows into columns and columns into rows.

### Text Functions
- **FIND vs SEARCH?** FIND is case-sensitive. SEARCH is not.
- **REPLACE vs SUBSTITUTE?** REPLACE works by position. SUBSTITUTE works by text.
- **CONCAT vs TEXTJOIN?** TEXTJOIN adds a delimiter and can skip empty cells.
- **TRIM vs CLEAN?** TRIM removes extra spaces. CLEAN removes line breaks and hidden characters.
- **Flash Fill vs formula?** Flash Fill copies a pattern but its results are fixed. A formula updates when data changes.

### Go To Special
- **Delete blank rows?** Ctrl + G > Special > Blanks > Ctrl + - > Entire row. Select one key column first.
- **Copy only visible cells?** Select > Alt + ; > Ctrl + C > Ctrl + V.
- **Compare two columns?** Select both > Ctrl + \\ (Row differences).
- **Precedents vs Dependents?** Precedents feed the cell. Dependents use the cell.

---

## 9. Common Excel Errors

| Error | Meaning |
|-------|---------|
| `#NAME?` | Typo in the function name (e.g. `=some`) |
| `#VALUE!` | Wrong data type, or FIND found nothing |
| `#DIV/0!` | Divided by zero |
| `#N/A` | Value not found |
| `#REF!` | A referenced cell was deleted |
| `#####` | Column is too narrow |

---

## 10. Quick Formula Reference

| Group | Functions |
|-------|-----------|
| Math | SUM, PRODUCT, AVERAGE, MAX, MIN, ROUND, RANK |
| Count | COUNT, COUNTA, COUNTBLANK |
| Extract | LEFT, RIGHT, MID |
| Clean and case | LEN, TRIM, CLEAN, UPPER, LOWER, PROPER |
| Join | CONCAT, CONCATENATE, TEXTJOIN, `&` |
| Find and replace | FIND, SEARCH, REPLACE, SUBSTITUTE |
| Convert | VALUE, TEXT, CHAR, CODE, REPT |
| Split (Microsoft 365) | TEXTSPLIT, TEXTBEFORE, TEXTAFTER |
| Sequences and dates | SEQUENCE, TODAY |

---

## Key Takeaway

Shortcuts save time, and understanding the difference between similar features (FIND vs SEARCH, Filter vs Conditional Formatting) is what interviews test.
