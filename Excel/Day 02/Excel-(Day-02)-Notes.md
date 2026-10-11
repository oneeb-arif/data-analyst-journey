# Day 02: Formulas, Functions and Conditional Formatting

## 1. Formula Basics

- **Formula:** you write it manually.
- **Function:** a predefined calculation built into Excel.
- Every formula starts with the **=** sign. It tells Excel to calculate.
- **How it works:** type `=` in A1, then click any cell (like B2). Its address appears in A1.
- A formula is built from: numbers, text, characters and **cell references**.

| Formula | Type | Behavior |
|---------|------|----------|
| `=100+200` | Hardcoded | Never changes |
| `=A1+B1` | Cell references | Updates dynamically when A1 or B1 changes |

---

## 2. Operators

| Formula | Action |
|---------|--------|
| `=A1+B1` | Add |
| `=A1-B1` | Subtract |
| `=A1*B1` | Multiply |
| `=A1/B1` | Divide |
| `=A1^2` | Power |
| `=A1&B1` | Join text |

**Tip:** always use cell references instead of typed numbers so results update automatically.

---

## 3. SUM and AutoSum

| Formula | Meaning |
|---------|---------|
| `=SUM(A2,B2)` | Add separate cells |
| `=SUM(A2:C2)` | Range: A2 + B2 + C2 |
| `=SUM(A1:A3)` | Continuous range (correct) |
| `=SUM(A1,A3)` | Only A1 and A3. It skips A2 (wrong for a continuous range) |

- **Start a function:** type `=SUM`, press **Tab** to accept it, then select the cells and press Enter.
- **AutoSum:** click the cell below your numbers, press **Alt + =**, then **Enter**.
- **Fill Handle:** drag the bottom-right corner of a cell to copy the formula down. References adjust automatically (A2+5, A3+5, A4+5).

---

## 4. Core Functions

| Formula | Action |
|---------|--------|
| `=PRODUCT(A2:C2)` | Multiply a range |
| `=AVERAGE(G3:H3)` | Average (arithmetic mean) |
| `=MAX(A2:C2)` | Largest value |
| `=MIN(A2:C2)` | Smallest value |
| `=ROUND(A1,2)` | Round to 2 decimals |
| `=TODAY()` | Today's date |

**Note:** `=A2*B2` and `=PRODUCT(A2:B2)` give the same answer. Use PRODUCT when you have a range.

---

## 5. COUNT Functions

Example row: `ab | 85 | 86 | (blank)`

| Formula | Counts | Result |
|---------|--------|--------|
| `=COUNT(C2:F2)` | Numbers only | 2 |
| `=COUNTA(C2:F2)` | Non-empty cells (numbers and text) | 3 |
| `=COUNTBLANK(C2:F2)` | Empty cells | 1 |

---

## 6. Shortcuts

| Shortcut | Action |
|----------|--------|
| Alt + = | AutoSum |
| Ctrl + Click | Select multiple cells (then delete, format, etc. on all of them) |
| Ctrl + Enter | Fill the same entry in all selected cells |
| Ctrl + G | Go To / Go To Special |
| Ctrl + H | Find and Replace |
| Ctrl + F | Find |
| F4 | Lock a cell reference (`$A$1`) |
| Ctrl + Z / Ctrl + Y | Undo / Redo |
| Ctrl + C / X / V | Copy / Cut / Paste |

**Fill blanks fast:** Ctrl + G > Special > Blanks > type `0` > Ctrl + Enter.

**Fill selected cells:** select cells with Ctrl + Click, type a value, then press Ctrl + Enter to apply it to all.

---

## 7. Paste Special

Press **Ctrl + Alt + V**, then press a letter, then Enter.

| Keys | Option |
|------|--------|
| Ctrl + Alt + V, then V | Values only (just the result) |
| Ctrl + Alt + V, then F | Formulas only |
| Ctrl + Alt + V, then T | Formats only (color, border) |
| Ctrl + Alt + V, then A | All (data, formulas, formatting) |
| Ctrl + Alt + V, then E | Transpose (rows <-> columns) |
| Ctrl + Alt + V, then M | Multiply (multiplies destination cells by the copied value) |
| Ctrl + Alt + V, then W | Column widths |

---

## 8. Conditional Formatting

**Concept:** cells are highlighted automatically based on a condition.
Example: sales above 50,000 turn green.

**Where:** Home tab > Styles > Conditional Formatting

**Steps**
1. Select the column (Ctrl + Shift + Down Arrow).
2. Go to Conditional Formatting > Highlight Cells Rules.
3. Pick a condition, set the value and color, click OK.

**Menu options**
- Highlight Cells Rules
- Top/Bottom Rules
- Data Bars
- Color Scales
- Icon Sets
- New Rule
- Clear Rules
- Manage Rules

---

## 9. Highlight Cells Rules

| Rule type | Options |
|-----------|---------|
| Numbers | Greater Than, Less Than, Between, Equal To |
| Text | Text that Contains |
| Dates | A Date Occurring (yesterday, today, tomorrow, last 7 days...) |
| Duplicates | Duplicate Values, Unique Values |

**Text Contains note:** it matches part of the text. If you highlight with the text `Arif`, both "Oneeb Arif" and "Anas Arif" are highlighted.

**Exact match fix:** Conditional Formatting > Manage Rules > Edit Rule > type the full name `Oneeb Arif` > OK.

**Date tips**
- Method 1: A2 = `10/10/2026`, then A3 = `=A2+1`
- Method 2 (if method 1 doesn't work): `=DATE(2026,10,20)`

---

## 10. Top/Bottom Rules

| Rule | Highlights |
|------|------------|
| Top 10 Items | Highest values |
| Top 10 % | Highest percent |
| Bottom 10 Items | Lowest values |
| Bottom 10 % | Lowest percent |
| Above Average | Values above the average |
| Below Average | Values below the average |

**Tip:** change the 10 to any number, like Top 3 or Bottom 5.

---

## 11. Data Bars, Color Scales and Icon Sets

- **Data Bars:** an in-cell bar. Bigger number = longer bar (e.g. 20, 50, 80, 100).
- **Color Scales:** background color changes by value. Low = Red, Medium = Yellow, High = Green (e.g. 20, 50, 100).
- **Icon Sets:** arrows or symbols by value. 80+ marks = High, 50 = Medium, 20 = Low.

---

## 12. Manage Rules

| Option | What it does |
|--------|--------------|
| New Rule | Build your own rule, including custom formulas |
| Manage Rules | See, edit, reorder or delete every rule on the sheet |
| Clear Rules | Remove rules from the selected cells or the entire sheet |

You can apply multiple conditions on a single column, and change the format from the rule's Format button.

---

## 13. Custom Number Formats

**Steps:** select the column > Ctrl + 1 > Number > Custom > type the code in the Type box > OK.

| Format code | Result |
|-------------|--------|
| `"PKR "#,##0.00` | PKR 1,250.50 |
| `"RS. "#,##0` | RS. 1,250 |
| `#,##0` | 1,250 |
| `0.00` | 1250.50 |
| `0%` | 45% |

Text goes inside quotes.

---

## 14. AI Add-ins in Excel (ChatGPT / Claude)

1. **Enable the Developer tab:** File > Options > Customize Ribbon > Main Tabs > tick **Developer** > OK.
2. **Get the add-in:** Developer tab > Add-ins > Open Store. Search for ChatGPT or Claude, then click Add. (A paid plan may be needed.)
3. **Use it:** the add-in appears on the Home tab. Sign in, select the cells or the sheet, type a prompt and it applies the operation.

Always double-check AI results before using them in a report.

---

## Practice Sheets

**COUNT demo:** `=COUNT(C2:F2)`, `=COUNTA(C2:F2)`, `=COUNTBLANK(C2:F2)` on student marks.

**Formulas demo (columns G to N):** `=SUM(D3,E3)`, `=E3-D3`, `=G3*H3`, `=PRODUCT(G3:H3)`, `=H3/G3`, `=AVERAGE(G3:H3)`, `=MAX(...)`, `=MIN(...)`.

**Conditional Formatting demo:** a sales and target table with Data Bars on Sales, highlight rules on Target, and Icon Sets for target status. Amounts shown in `Rs.` format.

---

## Key Takeaway

Use cell references and functions instead of typed numbers, so your results update automatically.
