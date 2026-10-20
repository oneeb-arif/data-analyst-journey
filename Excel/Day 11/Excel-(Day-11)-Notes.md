# Day 11: SUMIF, AVERAGEIF, COUNTIF and Attendance Tracker

## 1. SUMIF: The Idea

**SUMIF = SUM + IF.** It adds up a range, but only the values that match **one condition**.

**Example:** a sales sheet has 100 rows and 10 parties. You want the total sale of **Mr. X**.

**Why not Filter?** Filter is fine for a few parties. With 100 parties it is slow. In B2B, parties buy in chunks again and again, so SUMIF totals them instantly.

---

## 2. SUMIF Syntax

**Syntax:** `=SUMIF(range, criteria, sum_range)`

| Part | Meaning | Example |
|------|---------|---------|
| Range | Where to **search** | Party Name column in Master Data |
| Criteria | What to **find** | The party name in the Reporting table (Mr. X) |
| Sum range | Which values to **add** | Amount column in Master Data |

- **Master Data** holds all the rows.
- **Reporting** shows one line per party.

### Build It Step by Step
1. Type `=SUMIF(` in the Reporting cell.
2. Select all party names in Master Data, press **F4** to lock them, type a comma.
3. Click the party name in Reporting (do **not** lock it), type a comma.
4. Select all sales amounts, press **F4**, close the bracket and press Enter.

**Why F4?** The ranges must stay fixed when you drag the formula down. The criteria cell must move to the next party.

### SUMIF Examples

| Formula | Result |
|---------|--------|
| `=SUMIF(B:B,F2,C:C)` | Total sale of the party in F2 |
| `=SUMIF(C:C,">50000")` | Sum of sales above 50,000 |
| `=SUMIF(B:B,"Mr*",C:C)` | Total for names starting with Mr |
| `=SUMIF(C:C,">"&F1)` | Sum of values above the number in F1 |

- If `sum_range` is left out, SUMIF adds the range you searched.
- Operators go inside quotes. Use `&` to join an operator with a cell.

---

## 3. AVERAGEIF and COUNTIF

| Formula | Result |
|---------|--------|
| `=AVERAGEIF(B:B,F2,C:C)` | Average sale of party F2 |
| `=COUNTIF(B:B,F2)` | How many times party F2 came |
| `=COUNTIF(C:C,">50000")` | How many sales are above 50,000 |
| `=COUNTIF(B:B,"Mr*")` | How many names start with Mr |

- **AVERAGEIF** is written exactly like SUMIF: `=AVERAGEIF(range, criteria, average_range)`.
- **COUNTIF** needs only two parts: `=COUNTIF(range, criteria)`.

---

## 4. Criteria Tricks

| Criteria | Meaning |
|----------|---------|
| `"Mr. X"` | Exact text |
| `">50000"` | Greater than |
| `"<>Paid"` | Not equal to |
| `"Mr*"` | Starts with Mr |
| `"*Khan"` | Ends with Khan |
| `"?at"` | One letter, then "at" |

`*` means any number of characters and `?` means exactly one. Matching is **not** case-sensitive.

---

## 5. The "S" Versions (Many Conditions)

| Formula | Result |
|---------|--------|
| `=SUMIFS(C:C,B:B,F2,D:D,"East")` | Sum with 2 conditions |
| `=COUNTIFS(B:B,F2,D:D,"East")` | Count with 2 conditions |
| `=AVERAGEIFS(C:C,B:B,F2,D:D,"East")` | Average with 2 conditions |
| `=MAXIFS(C:C,B:B,F2)` | Biggest value for party F2 |
| `=MINIFS(C:C,B:B,F2)` | Smallest value for party F2 |

- In **SUMIFS** the **sum range comes first**.
- `MAXIFS` and `MINIFS` need Excel 2019 or newer.

---

## 6. Attendance Tracking System

Two ways to build it. Both use COUNTIF across Monday to Friday.

### Method 1: Checkboxes (Microsoft 365)
1. Select the cells for Monday to Friday.
2. Insert the checkboxes: **Insert tab > Checkbox**.
3. Ticked = `TRUE`, unticked = `FALSE`.

| Column | Formula |
|--------|---------|
| Present | `=COUNTIF(B2:F2,TRUE)` then drag down |
| Absent | `=COUNTIF(B2:F2,FALSE)` |

**Tip:** select a checkbox cell and press **Space** to tick or untick it.

### Method 2: Symbols (works in every Excel version)
1. Select the cells > Home > Font > **Wingdings 2**.
2. Type a capital **P** for a check mark and a capital **O** for an X.

| Column | Formula |
|--------|---------|
| Present | `=COUNTIF(B2:F2,"P")` |
| Absent | `=COUNTIF(B2:F2,"O")` |

The cell still holds the letter P or O. Only the font makes it look like a symbol.

### Make It Smarter
- **Attendance %:** `=COUNTIF(B2:F2,TRUE)/COLUMNS(B2:F2)`, then format as %.
- **Daily total:** `=COUNTIF(B2:B20,TRUE)` shows how many were present on Monday.
- **Highlight absent:** Conditional Formatting > Highlight Cells Rules > Equal To > FALSE.
- **Flag low attendance:** `=IF(H2>=75%,"OK","Short")`.

---

## 7. Shortcuts

| Shortcut | Action |
|----------|--------|
| F4 | Lock a range ($) |
| Ctrl + Shift + Down | Select column data |
| Ctrl + Space | Select the whole column |
| Space | Tick / untick a checkbox |
| Ctrl + D | Fill the formula down |
| Ctrl + A | Function Arguments dialog |
| Tab | Accept the function name |
| Ctrl + T | Make an Excel Table |

---

## 8. Cheat Sheet

| Group | Functions |
|-------|-----------|
| Conditional total | SUMIF, SUMIFS |
| Conditional average | AVERAGEIF, AVERAGEIFS |
| Conditional count | COUNTIF, COUNTIFS |
| Conditional min / max | MINIFS, MAXIFS |
| Attendance | Checkbox TRUE / FALSE, or Wingdings 2 with P and O |

---

## Key Takeaway

SUMIF, AVERAGEIF and COUNTIF turn a long Master Data sheet into a clean Reporting table in seconds. Lock the ranges with F4, and let the criteria cell move.
