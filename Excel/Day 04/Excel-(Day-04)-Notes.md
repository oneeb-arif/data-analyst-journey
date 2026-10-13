# Day 04: Go To Special, Paste Special and Cell References

## 1. Go To and Go To Special

**Move to a cell**
- **Name Box:** type the cell address (like D50) and press Enter.
- **Go To dialog:** Ctrl + G or F5, or Home > Find & Select > Go To. Type the reference > OK.

**Go To Special** selects only certain kinds of cells.

**Steps:** select the data range > Ctrl + G > Special > choose an option > OK.

| Option | Selects |
|--------|---------|
| Constants | Typed numbers and text (hardcoded values) |
| Formulas | Cells that contain a formula or function |
| Blanks | Empty cells |
| Visible cells only | Skips hidden or filtered rows (Alt + ;) |
| Current Region | The whole continuous data block or Table (Ctrl + Shift + *, like Ctrl + A) |
| Current Array | An array formula range, e.g. F117:G127 |
| Objects | All shapes at once (Insert > Shapes) |
| Conditional formats | Every cell that has a conditional formatting rule |
| Data validation | Cells that have dropdowns or validation rules |
| Row differences | Cells that differ across each row (Ctrl + \\) |
| Column differences | Cells that differ down each column (Ctrl + Shift + \|) |

Under **Constants** and **Formulas** you can also pick Numbers, Text, Logicals or Errors.

---

## 2. Constants vs Formulas

Click a cell and check the **Formula Bar**.

| Type | Constant | Formula |
|------|----------|---------|
| Formula Bar shows | The typed value | `= formula` |
| Example | `100` or `Ali` | `=A1+B1` |
| Logical | `TRUE` / `FALSE` typed | `=A1>5` (returns TRUE / FALSE) |
| Errors | `#N/A` typed | `=some` gives `#NAME?` |
| Changes when | You edit it | Its cells change |

---

## 3. Clear and Convert

| Shortcut | Action |
|----------|--------|
| Alt + H + E + A | Clear all (data + formatting) |
| Alt + H + E + F | Clear formatting only |
| Alt + H + E + C | Clear contents only (keeps formatting) |
| Ctrl + Alt + V, then V | Convert formulas to values |
| Ctrl + Shift + # | Apply date format |

- **Formulas to values:** select the range > Ctrl + C > Ctrl + Alt + V > V > Enter.
- **Dates showing as numbers:** pasted dates can appear as serial numbers. Select them and press Ctrl + Shift + #.

---

## 4. Delete Blank Rows

1. Select your data range.
2. Press Ctrl + G > Special > **Blanks** > OK.
3. Press **Ctrl + -** and choose **Entire row** > OK.

**Careful:** any row that has even one blank cell will be deleted. Select one key column (like ID) first.

---

## 5. Row and Column Differences

| Shortcut | Action |
|----------|--------|
| Ctrl + \\ | Row differences |
| Ctrl + Shift + \| | Column differences |

- **Row differences:** compares cells across each row. Select both columns, press Ctrl + \\. Cells that differ from the first column are selected.
- **Column differences:** compares cells down each column.
- **Example:** Column 1 = 1, 2, 3, 5 and Column 2 = 1, 3, 4, 5. Rows 2 and 3 differ, so they are selected.
- **Use case:** auditing and reconciling data, such as comparing invoice entries (e.g. INV-764512).

---

## 6. Visible Cells Only

**Problem:** copying a range that has hidden or filtered rows also copies the hidden rows.

**Fix**
1. Select the range.
2. Ctrl + G > Special > **Visible cells only** > OK (or press **Alt + ;**).
3. Ctrl + C, then Ctrl + V. Only visible cells are pasted.

**Bonus:** Go To Special > Conditional formats selects every cell on the sheet that has a conditional formatting rule.

---

## 7. Formula Auditing: Precedents and Dependents

- **Precedents:** which cells feed data into the selected formula. Example: 1000 = 50 x 20, so 50 and 20 are precedents.
- **Dependents:** which cells use the selected cell's value.

| Shortcut | Action |
|----------|--------|
| Alt + M + P | Trace Precedents (Formulas tab) |
| Alt + M + D | Trace Dependents |
| Alt + M + A | Remove arrows |
| Ctrl + [ | Select precedent cells |
| Ctrl + ] | Select dependent cells |
| Ctrl + ` | Show / hide all formulas |
| Ctrl + Home | First cell (A1) |
| Ctrl + End | Last used cell |

---

## 8. Paste Special: Math Operations

Calculate directly on a column without extra formula columns.

| Shortcut | Operation |
|----------|-----------|
| Ctrl + Alt + V, then D | Add |
| Ctrl + Alt + V, then S | Subtract |
| Ctrl + Alt + V, then M | Multiply |
| Ctrl + Alt + V, then I | Divide |

**Example: add 1000 to every salary**
1. Type 1000 in a cell and copy it (Ctrl + C).
2. Select the whole salary column.
3. Ctrl + Alt + V > **Add** > OK.

**Percentage trick:** marks like 65, 75, 85 can be turned into 0.65, 0.75, 0.85. Type 100 in a cell > copy it > select the marks > Paste Special > **Divide** > then format as % (Ctrl + Shift + %).

---

## 9. Paste Special Tools

| Shortcut | Option |
|----------|--------|
| Ctrl + Alt + V, then V | Values only (removes formulas) |
| Ctrl + Alt + V, then E | Transpose (rows <-> columns) |
| Ctrl + Alt + V, then L | Paste Link |
| Ctrl + Alt + V, then B | Skip blanks |
| Ctrl + Alt + V, then F | Formulas only |
| Ctrl + Alt + V, then A | All (data, formulas, formatting) |
| Ctrl + Alt + V, then T | Formats only |
| Ctrl + Alt + V, then X | All except borders |
| Ctrl + Alt + V, then W | Column widths |
| Ctrl + Alt + V, then R | Formulas and number formats |
| Ctrl + Alt + V, then U | Values and number formats |

- **Transpose:** horizontal to vertical, or vertical to horizontal.
- **Paste Link:** the pasted cells update automatically when the **source** cells change. It works across sheets and across workbooks.
- **Skip blanks:** blank cells in the copied range do not erase data that already exists in the destination. Useful when merging data.
- **Format Painter:** select styled data > click the brush icon (or Alt + H + F + P) > click the target cells. Double-click the brush to apply to many places.

---

## 10. Find and Replace

| Shortcut | Action |
|----------|--------|
| Ctrl + F | Find |
| Ctrl + H | Replace |
| Alt + A | Replace All (inside the dialog) |
| Alt + I | Find All (inside the dialog) |

Click **Options** for Match case, Match entire cell contents, search in Sheet or Workbook, and look in Formulas or Values.

**Wildcards:** `*` = any text, `?` = any single character.

---

## 11. Cell Referencing

**Why:** use cells instead of hardcoded numbers so values update automatically.
- `100+200 = 300` stays fixed.
- `A1+B1` changes when the cells change.

**The dragging issue:** when you drag a formula, references shift. Use proper ranges like `=SUM(C3:F3)`, or AutoSum (**Alt + =**).

| Type | Format | Behavior when dragged |
|------|--------|-----------------------|
| Relative | `A1` | Row and column both change |
| Absolute | `$A$1` | Row and column both locked |
| Mixed | `$A1` | Column locked, row changes |
| Mixed | `A$1` | Row locked, column changes |

The **$** sign locks whatever follows it.

**F4 shortcut:** with the cursor on a reference, press **F4** (or **Fn + F4** on many laptops). It cycles: `A1` > `$A$1` > `A$1` > `$A1` > `A1`.

---

## 12. Practical Example: Percentage

**Scenario:** marks of Person A, B, C, D divided by total marks allotted (400, stored in F1).

- Formula: `=G5/$F$1`, then drag down.
- `$F$1` stays fixed while `G5` moves to `G6`, `G7`...
- Without the `$` sign, F1 shifts to F2, F3 and the answers become wrong.
- Typing `400` directly also works, but if the total becomes 500 you must edit every cell. One cell reference fixes all.
- Format as a percentage: **Ctrl + Shift + %** (0.50 becomes 50%).

---

## Practice Sheets

- **Go To Special:** errors selection (`#NAME?`, `#VALUE!`), Objects (shapes), Visible cells only on filtered data, and Conditional formats.
- **Paste Special:** Skip blanks, Paste Link, Transpose and Find & Replace.
- **Clear:** original styled data compared with Clear Format, Clear Contents and Clear All.
- **Cell Referencing:** marksheet with Total Marks in `$J$3` used to calculate percentages for P.F, OOP, DSA and O.S.

---

## Key Takeaway

Lock the cell that must not move with `$` (press F4), and let Go To Special select exactly what you need.
