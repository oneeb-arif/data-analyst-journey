# Day 03: Clipboard, Filter, Sort, Tables and Fill Series

## 1. Clipboard Basics

| Shortcut | Action |
|----------|--------|
| Ctrl + C | Copy |
| Ctrl + X | Cut (removes data from the old location) |
| Ctrl + V | Paste (destination) |
| Ctrl + Alt + V | Paste Special |
| Win + V | Windows clipboard history |
| Esc | Cancel copy / cut mode |

**Office Clipboard:** Home tab > Clipboard group arrow. It stores up to 24 copied items. Click any item to paste it.

---

## 2. Move Data to Another Place

**Method 1: Cut and Paste**
1. Select the data (Ctrl + A or manual selection).
2. Ctrl + X removes it from the old location.
3. Go to the destination and press Ctrl + V.

**Method 2: Drag and Drop**
- Select the data and drag it by the **border** to move it.
- **Ctrl + drag** copies it.
- **Shift + drag** inserts it between existing cells.

**Between sheets:** copy or cut, switch sheet with Ctrl + PgDn, then paste (Sheet1 to Sheet2).

**Multiple cells:** hold Ctrl and click cells, then Ctrl + C. This works only if the selection lines up in the same rows or columns.

---

## 3. Filter

**Shortcut:** Ctrl + Shift + L

**Analogy:** dirty water > filter > clean water. Messy data > filter > only the data you need.

**How it works:** the master data has North, South, East and West. After filtering North, the other rows are hidden and you see only the required data.

| Filter | Conditional Formatting |
|--------|------------------------|
| Hides the other data and shows only what you need | Shows all data and only highlights the required part |

**Filter by Color:** filter rows by their highlight color.

### Filter and Sort Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl + Shift + L | Turn filter on / off |
| Alt + Down | Open the filter dropdown |
| Alt + A + C | Clear filter |
| Ctrl + Alt + L | Reapply filter |
| Alt + A + S + A | Sort A to Z (smallest first) |
| Alt + A + S + D | Sort Z to A (largest first) |
| Alt + A + S + S | Custom Sort (many levels) |

The filter dropdown also has a search box and Text, Number and Date filters. Key tips can vary by Excel version, so press Alt to check.

---

## 4. Sorting (Arrangement)

| Data type | Order |
|-----------|-------|
| Text | A to Z, Z to A |
| Date | Oldest to Newest, Newest to Oldest |
| Number | Ascending (smallest to largest), Descending (largest to smallest) |

- **Sort by Color:** similar to filter by color, but the data is **not hidden**.
- **Custom Sort:** sort by many levels, e.g. Department first, then Sales from largest to smallest.

---

## 5. Normal Data vs Excel Table (Ctrl + T)

| Feature | Normal Data | Excel Table |
|---------|-------------|-------------|
| Data growth | Fixed range | Auto-expands |
| Formatting | Manual | Automatic |
| Formulas | Not dynamic | Dynamic |
| Extra tab | None | Table Design |
| Filtering | Filter only | Filter + Slicer |
| Referencing | Cell references (A1:A10) | Structured references ([@Salary]) |
| Totals | Manual AutoSum | Total Row |

---

## 6. Creating a Table

**Three methods**
1. Select all > Home > Format as Table > pick a design.
2. Select all > Insert > Table (Alt + N + T).
3. Select all (Ctrl + A) > **Ctrl + T** > check "My table has headers" > OK.

**My Table Has Headers**
- Checked: the first row is treated as the header.
- Unchecked: the first row is treated as data, and Excel adds an extra header row (Column1, Column2...).

| Shortcut | Action |
|----------|--------|
| Ctrl + A | Select all data |
| Ctrl + T | Create table |
| Alt + N + T | Insert > Table |
| Ctrl + Shift + T | Show / hide Total Row |
| Alt + J + T + G | Convert table to range |
| Alt + H + H + N | Clear all cell colors (No Fill) |

---

## 7. Table Design Tab

Click anywhere inside the table and the **Table Design** tab appears.

| Option | What it does |
|--------|--------------|
| Header Row | Show or hide the header row |
| Total Row | Adds a total row at the bottom with built-in functions for each column |
| First Column | Applies bold formatting to the first column |
| Last Column | Applies bold formatting to the last column |
| Banded Rows | Alternating row shading |
| Banded Columns | Alternating column shading |
| Table Name | Top-left corner. Use a clear name like `SalesData` (no spaces) |

---

## 8. Dynamic Behavior and Slicer

- **Auto expansion:** when rows or columns are added, the table, formulas and formatting grow automatically.
- **Structured references:** formulas use names like `[@Salary]` instead of cell addresses.
- **Slicer:** an advanced, easier version of filter that works with buttons. Table Design > Insert Slicer. Ctrl + Click picks several items.
- **Convert back to a normal range:** Table Design > Tools > Convert to Range > OK (or Alt + J + T + G).

---

## 9. Table Limitations

- **Formula autofill:** a formula fills the whole column, which you may not always want.
- **Different references:** formulas show `[@Salary]`, not `B2`.
- **No merged cells** inside a table.
- **Custom layouts:** reports or print layouts may need extra adjusting.
- **Converting back** to a normal range takes extra steps.

---

## 10. Fill Series

**Supported types:** Number, Date (Day, Weekday, Month, Year) and Normal.

| Shortcut | Action |
|----------|--------|
| Alt + H + F + I + S | Fill Series dialog box |
| Ctrl + D | Fill down |
| Ctrl + R | Fill right |
| Alt + H + F + I + U | Fill up |
| Alt + H + F + I + L | Fill left |

**Dialog method:** Home > Editing > Fill > Series. Choose Rows or Columns, the type (Linear, Growth, Date), a Step value and a Stop value, then click OK.

### Linear Series (add / subtract)

| First value | Step | Result |
|-------------|------|--------|
| 1 | 2 | 1, 3, 5, 7 ... (stops at the Stop value) |
| 15 | -3 | 15, 12, 9, 6, 3 |

### Growth Series (multiply / divide)

| First value | Step | Result |
|-------------|------|--------|
| 2 | 2 | 2, 4, 8, 16, 32 |
| 10000 | 0.1 | 10000, 1000, 100, 10, 1 |

**Note:** Growth only multiplies. To divide by 10, use the decimal step **0.1**. A step of 10 would multiply by 10 instead.

---

## 11. SEQUENCE Function

**Syntax:** `=SEQUENCE(rows, columns, start, step)` then press Enter.

| Formula | Result |
|---------|--------|
| `=SEQUENCE(10)` | 1 to 10 down a column |
| `=SEQUENCE(5,5,1,5)` | 5 x 5 grid starting at 1 with step 5 |

Available in Excel 365 and Excel 2021 or newer.

---

## 12. Dates and Time

| Shortcut | Action |
|----------|--------|
| Ctrl + ; | Insert today's date (stays fixed) |
| Ctrl + Shift + ; | Insert the current time |

Use `=TODAY()` when you want a date that updates every day.

**Date Fill Series units**
- **Day:** adds 1 day each time.
- **Weekday:** skips Saturday and Sunday.
- **Month:** only the month increases. Example: 31-05-2026, 30-06-2026, 31-07-2026, 31-08-2026, 30-09-2026, 31-10-2026, 30-11-2026, 31-12-2026, 31-01-2027, 28-02-2027, 31-03-2027.
- **Year:** only the year increases (enter Step and Stop value).

---

## Practice Sheets

- **Filter:** filter dropdowns plus color filtering on a sales table (Date, Employee, Department, Region, Sales, Target).
- **Clipboard:** Office Clipboard panel used to collect and paste multiple copied items.
- **Table:** Excel Table with Department and Region slicers and a Total Row (total sales 3,225,105).
- **Fill:** Linear and Growth series, `=SEQUENCE(5,5,1,5)`, and Date fill with Day vs Weekday units.

---

## Key Takeaway

Turn your data into an Excel Table (Ctrl + T). It grows, formats and calculates by itself.
