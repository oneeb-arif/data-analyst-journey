# Day 05: F4 Toggle, RANK and Text Formulas

## 1. F4 Toggle (Cell Locking Modes)

Click on the reference inside the formula, then press **F4**. On many laptops use **Fn + F4**.

| Press | Result | Meaning |
|-------|--------|---------|
| 1st | `$G$3` | Row and column both locked (Absolute) |
| 2nd | `G$3` | Row locked, column can change (Mixed) |
| 3rd | `$G3` | Column locked, row can change (Mixed) |
| 4th | `G3` | Back to relative |

---

## 2. RANK Function

**Concept:** RANK checks one person's marks (or percentage) against everyone else's in a list to find their position.

| Person | Percentage | Rank |
|--------|-----------|------|
| A | 50% | 3rd |
| B | 60% | 2nd |
| C | 45% | 4th |
| D | 75% | 1st |

**Formula:** `=RANK(F5,$F$5:$F$19)`
- `F5` is the person's value. It stays **relative** and moves down as you drag.
- `$F$5:$F$19` is the whole list. It must be **absolute** so the list never shifts.

| Formula | Result |
|---------|--------|
| `=RANK(F5,$F$5:$F$19)` | Highest value = Rank 1 |
| `=RANK(F5,$F$5:$F$19,1)` | Lowest value = Rank 1 |
| `=RANK.EQ(F5,$F$5:$F$19)` | Same as RANK |

**Ties:** tied values share a rank, and the next rank is skipped. Two people at Rank 9 means the next person gets Rank 11.

---

## 3. Text Formula Rules

| Argument type | Rule | Example |
|---------------|------|---------|
| Numbers | No quotes | `100` |
| Cell references | No quotes | `A1` |
| Text | Must be in double quotes | `"Oneeb"` |

**Turn off Wrap Text:** Ctrl + 1 > Alignment tab > untick Wrap text.

---

## 4. Extract Text: LEFT, RIGHT, MID

Example name: `Mr. Oneeb Arif`

| Function | Syntax | Example | Result |
|----------|--------|---------|--------|
| LEFT | `=LEFT(text, [num_chars])` | `=LEFT(A1,3)` | Mr. |
| RIGHT | `=RIGHT(text, [num_chars])` | `=RIGHT(A2,4)` | Arif |
| MID | `=MID(text, start_num, num_chars)` | `=MID(A3,5,5)` | Oneeb |

More examples: `=RIGHT("Oneeb Arif",2)` gives `if`, and `=MID("Excel",2,3)` gives `xce`.

---

## 5. Measure, Clean and Change Case

| Function | Syntax | Example | Result |
|----------|--------|---------|--------|
| LEN | `=LEN(text)` | `=LEN("Oneeb")` | 5 |
| TRIM | `=TRIM(text)` | `=TRIM(" Hello ")` | Hello |
| UPPER | `=UPPER(text)` | `=UPPER("abcd")` | ABCD |
| LOWER | `=LOWER(text)` | `=LOWER("ABCD")` | abcd |
| PROPER | `=PROPER(text)` | `=PROPER("oneeb arif")` | Oneeb Arif |

- **LEN** counts spaces too. Great for checking phone numbers and IDs (e.g. `AXP-7842-MNO` = 12 characters).
- **TRIM** removes extra spaces at the start, at the end and between words.

---

## 6. Join Text

**Example:** A1 = Oneeb, B1 = Arif. Required output: `Oneeb Arif`.

**Space problem:** Excel adds no space by itself. Put `" "` in the middle.

| Method | Formula | Result |
|--------|---------|--------|
| CONCATENATE | `=CONCATENATE(A1," ",B1)` | Oneeb Arif |
| CONCAT | `=CONCAT(A1,"-",B1)` | Oneeb-Arif |
| TEXTJOIN | `=TEXTJOIN(" ",TRUE,A1,B1)` | Oneeb Arif |
| Ampersand (&) | `=A1&" "&B1` | Oneeb Arif |

- **CONCAT** is the modern version of CONCATENATE. It also accepts ranges like `A1:C1`.
- **Delimiter:** the character between joined text (a space, `-` or `,`).

### TEXTJOIN

**Syntax:** `=TEXTJOIN(delimiter, ignore_empty, text1, [text2], ...)`

- **TRUE:** skips empty cells. No middle name means no extra space.
- **FALSE:** keeps empty cells, so you get an extra space or separator.

---

## 7. Flash Fill and Text Tools

| Shortcut | Action |
|----------|--------|
| Ctrl + E | Flash Fill |
| Alt + A + E | Text to Columns |
| Alt + Enter | New line inside a cell |
| Ctrl + 1 | Format Cells box |
| Ctrl + Shift + U | Expand / collapse the formula bar |

**Flash Fill steps:** type the first result (e.g. `Oneeb Arif`) > press Enter > press **Ctrl + E**. Excel detects the pattern and fills the rest.

**Note:** Flash Fill gives fixed results. It does not update if the source data changes.

---

## 8. Split Text (Microsoft 365)

| Function | Example | Result |
|----------|---------|--------|
| TEXTSPLIT | `=TEXTSPLIT(A1," ")` | Oneeb \| Arif (two cells) |
| TEXTBEFORE | `=TEXTBEFORE(A1," ")` | Oneeb |
| TEXTAFTER | `=TEXTAFTER(A1," ")` | Arif |

These work in Microsoft 365 and newer Excel versions only. TEXTSPLIT spills into the cells next to it. In older Excel use **Text to Columns** (Alt + A + E) or **Flash Fill**.

---

## 9. FIND vs SEARCH

| Function | Case | Syntax |
|----------|------|--------|
| FIND | Case-sensitive | `=FIND(find_text, within_text, [start_num])` |
| SEARCH | Not case-sensitive (allows wildcards) | `=SEARCH(find_text, within_text, [start_num])` |

| Formula | Result |
|---------|--------|
| `=FIND("A","EIM-4532-ABC")` | 10 |
| `=FIND("a","Oneeb arif")` | 7 |
| `=SEARCH("A","Oneeb arif")` | 7 |
| `=FIND("A","Oneeb arif")` | #VALUE! (no capital A) |
| `=SEARCH("O","AXP-7842-MNO")` | 12 |

Both return the position of the **first** match, and `#VALUE!` if nothing is found.

---

## 10. REPLACE vs SUBSTITUTE

ID = `AXP-7842-MNO`

| Function | Works by | Syntax |
|----------|----------|--------|
| REPLACE | Position | `=REPLACE(old_text, start_num, num_chars, new_text)` |
| SUBSTITUTE | Text | `=SUBSTITUTE(text, old_text, new_text, [instance_num])` |

| Formula | Result |
|---------|--------|
| `=REPLACE(H77,5,4,2026)` | AXP-2026-MNO |
| `=SUBSTITUTE(B77,"-","@")` | AXP@7842@MNO |
| `=SUBSTITUTE(B77,"-","@",1)` | AXP@7842-MNO (first only) |
| `=SUBSTITUTE(B77,"-","@",2)` | AXP-7842@MNO (second only) |

---

## 11. TEXT Function

**Syntax:** `=TEXT(value, format_text)`. The result is text, not a number.

Date in B92 = `10/14/2026`

| Formula | Result |
|---------|--------|
| `=TEXT(B92,"DDDD")` | Wednesday |
| `=TEXT(B92,"DD DDD")` | 14 Wed |
| `=TEXT(B92,"MMMM")` | October |
| `=TEXT(1234.5,"#,##0.00")` | 1,234.50 |
| `=TEXT(0.45,"0%")` | 45% |

**Adding words:** words inside a format need extra quotes, e.g. `=TEXT(100,"""Rs ""0")` shows `Rs 100`. (A plain `"Rs0"` can fail because `s` means seconds.)

---

## 12. VALUE, CLEAN, CHAR, REPT

| Function | Example | Result |
|----------|---------|--------|
| VALUE | `=VALUE(B44)` | Text `'1234` (left) becomes number 1234 (right) |
| CLEAN | `=CLEAN(B45)` | `OneebArif` (line break removed) |
| CHAR | `=CHAR(65)` | A |
| CODE | `=CODE("A")` | 65 |
| REPT | `=REPT("*",5)` | ***** |

- Text aligns **left**, numbers align **right**.
- CLEAN removes line breaks (Alt + Enter) but joins the words. To keep a space use `=SUBSTITUTE(B45,CHAR(10)," ")`.
- REPT is great for in-cell bars and rating stars.

---

## 13. Text Functions Cheat Sheet

| Group | Functions |
|-------|-----------|
| Extract | LEFT, RIGHT, MID |
| Measure and clean | LEN, TRIM, CLEAN |
| Change case | UPPER, LOWER, PROPER |
| Join | CONCAT, CONCATENATE, TEXTJOIN, & |
| Find and replace | FIND, SEARCH, REPLACE, SUBSTITUTE |
| Convert and repeat | VALUE, TEXT, CHAR, REPT |
| Split (Microsoft 365) | TEXTSPLIT, TEXTBEFORE, TEXTAFTER |

---

## Practice Sheet: Marksheet, Percentage and Rank

- **Total Marks:** `=SUM(B5:E5)`
- **Percentage:** `=F5/$G$3` (400 locked with F4)
- **Rank:** `=RANK(F5,$F$5:$F$19)` (range locked)

| Result | Details |
|--------|---------|
| Rank 1 | Bilal Hussain, 311 marks (78%) |
| Rank 2 | Muhammad Hamza, 272 marks (68%) |
| Rank 3 | Ali Abbas, 269 marks (67%) |
| Tie | Fatima Ali and Maryam Sheikh both scored 187 (47%), so both got Rank 9 |

---

## Key Takeaway

Lock the list with F4 for RANK, and let text functions clean, split and join your data in seconds.
