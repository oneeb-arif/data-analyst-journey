# Day 01: Excel Basics, Navigation and Formatting

## 1. Excel Basics

- Every business (staff, marketing, owner, maintenance) runs on data.
- Flow: **Record information (data entry) -> Analyze -> Take the right decision**
- Rows: **1,048,576** (numbered)
- Columns: **16,384** (lettered A to XFD)
- One file = one **workbook**. A workbook has many **sheets** (pages).
- Data types: Number, Text, Character, Date, Time
- Fill series: type 1, 2, 3 and drag the corner to continue the series.

---

## 2. Interface

| Element | What it does |
|---------|--------------|
| Ribbon | Tabs > Groups > Dialog Launcher (small arrow at the group corner) |
| Name Box | Shows the active cell address (e.g. A1) |
| Formula Bar | Whatever you type in the cell or the bar shows in both |
| Sheet Name | Double-click the sheet tab (or right-click > Rename) |
| Views | Normal, Page Break / Print view, Zoom (+ / -) |
| Alt key | Shows Key Tips on the ribbon (H = Home tab) |

---

## 3. Navigation Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl + Tab | Next workbook |
| Win + Tab | Task View (all windows) |
| Ctrl + PgDn | Next sheet |
| Ctrl + PgUp | Previous sheet |
| Tab | Move right |
| Enter | Move down |
| Shift + Tab | Move left |
| Shift + Enter | Move up |
| Ctrl + Home | First cell (A1) |
| Ctrl + End | Last used cell |
| Ctrl + Arrow | Jump to the edge of data |
| Ctrl + G (or F5) | Go To any cell |
| F2 | Edit the cell (End = go to the end of text) |

---

## 4. Selection

| Shortcut | Action |
|----------|--------|
| Ctrl + A | Select all data |
| Ctrl + Shift + Arrow | Select till the end of data |
| Shift + Arrow | Select cell by cell |
| Shift + Space | Select entire row |
| Ctrl + Space | Select entire column |

**Notes**
- Ctrl + A and Ctrl + Shift + Arrow only travel through **connected** cells. They stop at a gap.
- **Multiple sheets:** click the first sheet, hold Shift, click the last sheet. A change in one sheet applies to all selected sheets.

---

## 5. Rows, Columns and Sizing

| Shortcut | Action |
|----------|--------|
| Ctrl + Shift + + | Insert row / column / cells (select first) |
| Ctrl + - | Delete row / column / cells (select first) |
| Alt + H + O + A | AutoFit row height |
| Alt + H + O + I | AutoFit column width |
| Ctrl + D | Fill down |
| Ctrl + R | Fill right |

**Tip:** Double-click a column border for a quick AutoFit.

---

## 6. Font Formatting

| Shortcut | Action |
|----------|--------|
| Ctrl + B (or Ctrl + 2) | Bold |
| Ctrl + I (or Ctrl + 3) | Italic |
| Ctrl + U (or Ctrl + 4) | Underline |
| Ctrl + 5 | Strikethrough |
| Alt + H + F + F | Change font style |
| Alt + H + F + S | Change font size |
| Ctrl + 1 | Format Cells dialog box |

**Industry-favourite fonts:** Calibri, Arial, Aptos, Segoe UI. Keep one font per sheet.

---

## 7. Alignment

- Default: **text aligns left, numbers align right.**

| Shortcut | Action |
|----------|--------|
| Alt + H + A + C | Center |
| Alt + H + A + M | Middle |
| Alt + H + A + T | Top |
| Alt + H + A + B | Bottom |
| Alt + H + 6 | Increase indent |
| Alt + H + 5 | Decrease indent |
| Alt + H + W | Wrap text |

---

## 8. Merge Cells

| Shortcut | Action |
|----------|--------|
| Alt + H + M + C | Merge & Center |
| Alt + H + M + A | Merge Across |
| Alt + H + M + M | Merge Cells |
| Alt + H + M + U | Unmerge |

**Note:** Merging keeps only the first cell (A1 + B1 = A1).

**Wrap Text vs Shrink to Fit**
- Wrap Text: makes the cell taller so the text fits. Width stays the same.
- Shrink to Fit: makes the text smaller so it fits. Cell size stays the same.

---

## 9. Borders and Colors

| Shortcut | Action |
|----------|--------|
| Alt + H + B + A | All borders |
| Alt + H + B + T | Thick outside border |
| Alt + H + B + M | More borders |
| Alt + H + B + N | No border |
| Alt + H + F + C | Font color |
| Alt + H + F + P | Format Painter |
| Ctrl + Alt + V | Paste Special |

- **Cell color** = paint bucket icon.
- **Font color** = letter A with a color bar.
- **Copy a format:** Ctrl + C, select the target cell, then Ctrl + Alt + V > Formats.

---

## 10. Number Formats

| Shortcut | Action |
|----------|--------|
| Ctrl + Shift + ! | Number (1,000.00) |
| Ctrl + Shift + $ | Currency |
| Ctrl + Shift + % | Percentage |
| Ctrl + Shift + ~ | General |
| Ctrl + Shift + # | Date |
| Ctrl + Shift + @ | Time |
| Alt + H + 0 | Increase decimal |
| Alt + H + 9 | Decrease decimal |

**Readability:** 364335 is hard to read. 364,335.00 is easy.

**Currency vs Accounting**
- Currency: `PKR 335.00` (symbol sits right next to the number)
- Accounting: `PKR      335.00` (symbol on the left edge, amount on the right edge)

**Scientific numbers:** very long numbers (11+ digits) turn into scientific format (e.g. 2E+11). Set the cell to **Text** first, then type the number.

---

## 11. Date Formats

Example date: **Saturday, 10 October 2026**

| Format code | Result |
|-------------|--------|
| DD-MM-YY | 10-10-26 |
| D-M-YY | 4-4-26 |
| DDD-MMM-YYYY | Sat-Oct-2026 |
| DDDD-MMMM-YYYY | Saturday-October-2026 |
| DD/MM/YYYY | 01/04/2026 |
| DD/MMM/YY | 01/Apr/26 |

- Days: Mon, Tue, Wed, Thu, Fri, Sat, Sun
- Months: Jan, Feb, Mar, Apr, May, Jun, Jul, Aug, Sep, Oct, Nov, Dec

**Apply a custom format**
1. Select the column with Ctrl + Space.
2. Open the Number Dialog Launcher (or press Ctrl + 1).
3. Click **Custom**.
4. Write the format code in the **Type** box.
5. Click **OK**.

---

## 12. Create Your Own Shortcut (Quick Access Toolbar)

1. Right-click any command (e.g. Merge & Center) > **Add to Quick Access Toolbar**.
2. Press **Alt**. A number appears on every icon in the toolbar.
3. Press **Alt + that number**. That is your own shortcut.
4. To reorder: **File > Options > Quick Access Toolbar**. Order decides the number.

**Tip:** Put your most-used command first. It becomes **Alt + 1**.

---

## Key Takeaway

In Excel, speed comes from the keyboard, not the mouse.
