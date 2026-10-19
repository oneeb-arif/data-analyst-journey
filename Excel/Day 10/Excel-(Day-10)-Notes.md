# Day 10: Logical Formulas (IF, AND, OR, IFS, SWITCH, IFERROR and IS functions)

## 1. Logical Test

- A **logical test** is a condition Excel checks, like "is the percentage 33% or more?"
- The answer is always **TRUE or FALSE** (Boolean). Behind the scenes TRUE = 1 and FALSE = 0.
- Example: marks of 50% against the 33% rule = TRUE, so the result is Pass.

### Comparison Operators

| Operator | Meaning |
|----------|---------|
| `=` | Equal to |
| `<>` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |

Example: `=B2>=33%` returns TRUE or FALSE. Text in a condition must be inside quotes, like `=A1="Paid"`.

---

## 2. IF Function

**Syntax:** `=IF(logical_test, value_if_true, value_if_false)`

**Pass / Fail example:** `=IF(B2>=33%,"Pass","Fail")`

| Person | Percentage | Result |
|--------|-----------|--------|
| A | 50% | Pass |
| B | 30% | Fail |
| C | 70% | Pass |
| D | 20% | Fail |
| E | 80% | Pass |

**Steps Excel follows**
1. Take A's marks.
2. Set the condition (33%).
3. Apply the condition (logical test).
4. If TRUE, give `"Pass"` (value if true).
5. If FALSE, give `"Fail"` (value if false).

**Text rule:** text results go inside double quotes. Numbers and cell references do not.

### More IF Examples

| Formula | Result |
|---------|--------|
| `=IF(C33="","Pending","Payment Done")` | Blank = Pending, anything typed = Payment Done |
| `=IF(A1>=100,A1+B1,B1-A1)` | 600 when A1 = 100 and B1 = 500 |

Empty quotes `""` mean a blank cell. If C33 is blank the answer is Pending. If it holds `123` the answer is Payment Done.

---

## 3. AND, OR and NOT

| Function | Rule |
|----------|------|
| AND | **All** conditions must be TRUE |
| OR | **Any one** condition is enough |
| NOT | Flips TRUE to FALSE and the other way round |

**Bonus rule:** sales >= 50,000 and rating >= 3.

Formula: `=AND(D24>=50000,E24>=3)` gives TRUE or FALSE. OR is written the same way.

| Person | Sales | Rating | AND | OR |
|--------|-------|--------|-----|----|
| A | 30,000 | 4 | FALSE | TRUE |
| B | 60,000 | 5 | TRUE | TRUE |
| C | 40,000 | 2 | FALSE | FALSE |

### IF with AND / OR

| Formula | Meaning |
|---------|---------|
| `=IF(AND(D24>=50000,E24>=3),"Bonus Eligible","No Bonus")` | Both conditions needed |
| `=IF(OR(D24>=50000,E24>=3),"Bonus Eligible","No Bonus")` | Any one condition is enough |

AND or OR gives TRUE or FALSE, and IF turns that answer into words.

---

## 4. Nested IF

**Rating rule:** 70,000+ = 5, 60,000+ = 4, 50,000+ = 3, 40,000+ = 2, otherwise 1.

```
=IF(D24>=70000,5,IF(D24>=60000,4,IF(D24>=50000,3,IF(D24>=40000,2,1))))
```

- **Order matters.** Start from the highest condition. Excel stops at the first TRUE.
- **Brackets:** close one `)` for every IF you open. Here there are 4 IFs, so 4 closing brackets.

---

## 5. IFS Function

- **IF** checks one condition. **IFS** checks many conditions in a row, with no nesting.
- **Syntax:** `=IFS(test1, result1, test2, result2, ...)`

**Grade example (shortened):**

```
=IFS(K4>=90%,"A",K4>=80%,"B",K4>=70%,"C",K4>=60%,"D",TRUE,"F")
```

**The TRUE trick:** if every earlier test is FALSE, `TRUE` catches the rest and returns `"F"`. Without it you get `#N/A`.

**Full grading scale used in class:**

| Percentage | Grade |
|-----------|-------|
| 95% or more | A+ |
| 90% | A |
| 85% | A- |
| 80% | B+ |
| 75% | B |
| 70% | B- |
| 65% | C+ |
| 60% | C |
| 55% | C- |
| 50% | D |
| Below 50% | F |

**Where to use IFS:** grades (marks and percentage), bonus percentage by sales, tax slabs (income decides the tax %).

**Remember:** put the highest condition first and finish with `TRUE` for "everything else". IFS works in Excel 2019 and newer.

---

## 6. SWITCH Function

**Syntax:** `=SWITCH(expression, value1, result1, value2, result2, ..., default)`

**Example:** `=SWITCH(A1,"A+",5000,"A",3000,"B",1000,0)`

- Grade A+ gives 5000, A gives 3000, B gives 1000, anything else gives 0 (the default).
- **SWITCH** matches **exact values** only. **IFS** is for ranges like `>= 80%`.

---

## 7. IFERROR and IFNA

- **Problem:** `50 / 0` gives `#DIV/0!`, which looks bad in reports.
- **Fix:** `=IFERROR(F90/F91,"Value is Wrong")` shows your message instead of the error.
- **Why useful:** keeps automation sheets and trackers clean.
- **IFNA:** `=IFNA(value, message)` hides only `#N/A`. IFERROR hides **every** error, so use it carefully.

---

## 8. IS Functions

They check something and answer TRUE or FALSE.

| Formula | Checks |
|---------|--------|
| `=ISBLANK(C33)` | Cell is empty |
| `=ISNUMBER(A1)` | Cell holds a number |
| `=ISTEXT(A1)` | Cell holds text |
| `=ISERROR(A1)` | Cell shows any error |
| `=ISNA(A1)` | Cell shows `#N/A` only |
| `=ISLOGICAL(A1)` | Cell holds TRUE or FALSE |
| `=ISFORMULA(A1)` | Cell contains a formula |
| `=ISEVEN(50)` | TRUE (also `ISODD(7)`) |

They pair well with IF: `=IF(ISBLANK(C33),"Pending","Done")`.

---

## 9. Shortcuts

| Shortcut | Action |
|----------|--------|
| Tab | Accept the function name |
| Ctrl + A | Function Arguments dialog box |
| Alt + Enter | Line break inside a formula |
| Ctrl + Shift + U | Expand the formula bar |
| Alt + M + V | Evaluate Formula |
| F9 | Show the value of the selected part |
| F4 | Lock a reference |
| Shift + F3 | Insert Function dialog |

**Tip:** type `=IF`, press **Tab** to get `=IF(`, then press **Ctrl + A**. The dialog box lets you fill each part of a big formula.

---

## 10. Cheat Sheet

| Group | Functions |
|-------|-----------|
| Decide | IF, IFS, SWITCH |
| Combine conditions | AND, OR, NOT |
| Handle errors | IFERROR, IFNA |
| Check type | ISBLANK, ISNUMBER, ISTEXT, ISLOGICAL, ISERROR, ISNA, ISFORMULA, ISEVEN, ISODD |
| Operators | `=`  `<>`  `>`  `<`  `>=`  `<=` |

---

## Key Takeaway

IF decides, AND and OR combine conditions, IFS replaces long nested IFs, and IFERROR keeps your reports clean.
