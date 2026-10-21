# Day 12: SUMIFS, AVERAGEIFS, COUNTIFS and Excel Errors

## 1. SUMIFS: The Idea

- **SUMIF** has one condition. **SUMIFS** has as many as you need.
- **Example:** a report with **Supplier Names** down the side and **Months** across the top. Each cell needs two conditions.

**Syntax:**

```
=SUMIFS(sum_range, criteria_range1, criteria1, criteria_range2, criteria2, ...)
```

**Big difference:** in SUMIFS the **sum range comes first**. In SUMIF it comes last.

---

## 2. Set Up the Report

| Part | What it holds |
|------|---------------|
| Master Data | One row per sale: Date, Month, Supplier Name, Product, Category, Region, City, Province, Gender, Sales |
| Report rows | Every Supplier Name listed once (unique) |
| Report columns | Every Month listed once (Oct, Nov, Dec, Jan ... Sep) |
| Total column | `=SUM(B3:M3)` adds all months for one supplier |

---

## 3. Build SUMIFS Step by Step

1. Type `=SUMIFS`, press **Tab**, then **Ctrl + A** to open the Function Arguments box.
2. **Sum_range:** Master Data > Sales column. Press **F4** to lock it.
3. **Criteria_range1:** Supplier Names in Master Data (F4).
4. **Criteria1:** the supplier names in your report.
5. **Criteria_range2:** Months in Master Data (F4).
6. **Criteria2:** the months in your report.
7. Click **OK**. The result is shown.

### The Real Formula (from the practice sheet)

```
=SUMIFS('Master Data'!$K$2:$K$101,'Master Data'!$D$2:$D$101,A3:A17,'Master Data'!$C$2:$C$101,B2:M2)
```

- **Microsoft 365:** one formula in B3 fills the whole table (it spills). No dragging is needed, because `A3:A17` and `B2:M2` are full ranges.
- **Older Excel:** use mixed references and drag right and down:

```
=SUMIFS('Master Data'!$K$2:$K$101,'Master Data'!$D$2:$D$101,$A3,'Master Data'!$C$2:$C$101,B$2)
```

- `$A3` locks the supplier column. `B$2` locks the month row.

---

## 4. AVERAGEIFS and COUNTIFS

| Formula | Result |
|---------|--------|
| `=AVERAGEIFS(K:K,D:D,$A3,C:C,B$2)` | Average sale with 2 conditions |
| `=COUNTIFS(D:D,$A3,C:C,B$2)` | Count of sales with 2 conditions |
| `=COUNTIF(B3:M3,">0")` | Number of months with sales |
| `=IFERROR(AVERAGEIFS(...),0)` | 0 when there were no sales |

- **AVERAGEIFS** is written like SUMIFS (average range first). Just change `SUMIFS` to `AVERAGEIFS`.
- **COUNTIFS** has no sum range, only pairs: `=COUNTIFS(criteria_range1, criteria1, criteria_range2, criteria2)`.
- `COUNT` cannot take a condition. Use **COUNTIF** for something like `">0"`.

### Report Tips
- **Zeros as dashes:** the Accounting number format shows 0 as a dash.
- **Avoid #DIV/0!:** AVERAGEIFS fails when a supplier had no sales that month. Wrap it in IFERROR.
- **Totals:** row total `=SUM(B3:M3)`, column total `=SUM(B3:B17)`.
- **Check your work:** the grand total must equal `=SUM(K2:K101)` from Master Data.

---

## 5. Excel Errors

| Error | Meaning | Example |
|-------|---------|---------|
| `#DIV/0!` | Dividing by 0 or a blank cell | `=10/0` |
| `#VALUE!` | Wrong data type used in a formula | `="Ali"+5` |
| `#NAME?` | Formula name written wrongly | `=SUMM(A1:A5)` |
| `#REF!` | A referenced cell was deleted or is invalid | `=A1+B1`, then delete column B |
| `#N/A` | Required value is not available | `=VLOOKUP(100,A2:B5,2,FALSE)` when 100 is not found |
| `#NUM!` | Invalid numerical calculation | `=SQRT(-1)` |
| `#NULL!` | Wrong range intersection | `=SUM(A2:A3 C1:C3)` (a space between ranges) |

### More Errors You Will Meet
- **`#####`:** the column is too narrow (or a date is negative). Double-click the column border to widen it.
- **`#SPILL!`:** a spilling formula, like the SUMIFS report, is blocked by data in its way. Clear the cells in its path.
- **Green triangle:** Excel flags a possible problem. Click it for options like Trace Error.

---

## 6. Fix Errors in Bulk

1. Select the range, copy it and paste values (**Ctrl + Alt + V, then V**). The errors become constants.
2. Press **Ctrl + G > Special > Constants**.
3. Untick **Numbers, Text and Logicals**. Keep only **Errors** > OK. Every error cell is highlighted automatically.
4. Type `0` (or any value) and press **Ctrl + Enter**. All errors are replaced at once.

**Better still:** prevent errors with IFERROR before they appear.

### Handle Errors with Formulas

| Formula | Result |
|---------|--------|
| `=IFERROR(10/0,0)` | 0 |
| `=IFERROR(A1/B1,"")` | Blank instead of an error |
| `=IF(B1=0,0,A1/B1)` | Avoids #DIV/0! before it happens |
| `=ISERROR(A1)` | TRUE or FALSE |

IFERROR hides **every** error, including real mistakes. Use IF to avoid a known problem like dividing by zero.

---

## 7. Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl + A | Function Arguments dialog |
| Tab | Accept the function name |
| F4 | Lock a range ($) |
| Ctrl + G | Go To / Go To Special |
| Ctrl + Enter | Fill all selected cells |
| Ctrl + Alt + V, then V | Paste values only |
| Alt + M + V | Evaluate Formula |
| Ctrl + Space | Select the whole column |

---

## 8. Cheat Sheet

| Group | Functions |
|-------|-----------|
| Multiple conditions | SUMIFS, AVERAGEIFS, COUNTIFS |
| Min / Max by condition | MINIFS, MAXIFS |
| Handle errors | IFERROR, IFNA, ISERROR, IF |
| Error types | #DIV/0!, #VALUE!, #NAME?, #REF!, #N/A, #NUM!, #NULL!, #SPILL! |

---

## Key Takeaway

SUMIFS turns Master Data into a full Supplier x Month report, and knowing what each error means helps you fix problems fast.
