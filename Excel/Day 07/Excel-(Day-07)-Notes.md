# Day 07: Random Numbers, Rounding, LARGE and SMALL

## 1. Random Number Functions

| Function | Result |
|----------|--------|
| `=RAND()` | Random decimal between 0 and 1 |
| `=RANDBETWEEN(bottom, top)` | Random whole number between two values |
| `=RANDARRAY([rows],[columns],[min],[max],[whole_number])` | A grid of random numbers (spills) |

**Examples**
- `=RANDBETWEEN(1,100)`: a whole number from 1 to 100.
- `=RANDARRAY(10,3,0,100,TRUE)`: 10 rows x 3 columns of whole numbers from 0 to 100.
- `=RANDARRAY()`: a single random decimal between 0 and 1.

**Notes**
- In `RANDBETWEEN`, the **smallest number comes first** (bottom, then top).
- `RANDARRAY` works in Microsoft 365 and Excel 2021 or newer.

---

## 2. Why Random Numbers Keep Changing

- These functions are **volatile**. They get new numbers every time the sheet recalculates.
- `TODAY()` and `NOW()` are volatile too.
- **Recalculate:** press **F9**.
- **Freeze the numbers:** copy them, then Ctrl + Alt + V > V > Enter (Paste Values).

---

## 3. ROUND

**Syntax:** `=ROUND(number, num_digits)`

| Formula | Result |
|---------|--------|
| `=ROUND(186.74648,3)` | 186.746 |
| `=ROUND(186.74648,2)` | 186.75 |
| `=ROUND(186.74648,0)` | 187 |
| `=ROUND(186.74648,-1)` | 190 |
| `=ROUND(186.74648,-2)` | 200 |

- Positive `num_digits` = decimal places.
- `0` = whole number.
- Negative `num_digits` = rounds to the left of the decimal point (tens, hundreds).
- A digit of 5 or more rounds up.

---

## 4. ROUNDUP and ROUNDDOWN

| Formula | Result |
|---------|--------|
| `=ROUNDUP(186.74648,3)` | 186.747 |
| `=ROUNDUP(186.74648,0)` | 187 |
| `=ROUNDDOWN(186.74648,3)` | 186.746 |
| `=ROUNDDOWN(186.74648,1)` | 186.7 |
| `=ROUNDDOWN(186.74648,0)` | 186 |

- ROUNDUP always moves **away from zero**.
- ROUNDDOWN always moves **toward zero**.
- There is no "5 rule" like in ROUND.

---

## 5. INT vs TRUNC

| Formula | Result |
|---------|--------|
| `=INT(186.74648)` | 186 |
| `=TRUNC(186.74648)` | 186 |
| `=TRUNC(186.74648,1)` | 186.7 |
| `=INT(-5.5)` | -6 |
| `=TRUNC(-5.5)` | -5 |

- **INT** rounds down to the next lower whole number.
- **TRUNC** simply cuts off the decimals, and can keep some decimals (`=TRUNC(number, digits)`).
- They give the same result for positive numbers, but differ for negative numbers.

---

## 6. LARGE and SMALL

**Syntax:** `=LARGE(array, k)` and `=SMALL(array, k)`, where `k` is the position you want.

Data in B2:B11: `821, 486, 528, 128, 422, 206, 342, 296, 813, 330`

| Formula | Result |
|---------|--------|
| `=LARGE(B2:B11,1)` | 821 (biggest) |
| `=LARGE(B2:B11,2)` | 813 |
| `=LARGE(B2:B11,3)` | 528 |
| `=SMALL(B2:B11,1)` | 128 (smallest) |
| `=SMALL(B2:B11,2)` | 206 |

- `LARGE(range,1)` is the same as `MAX`.
- `SMALL(range,1)` is the same as `MIN`.
- If `k` is bigger than the number of values, you get `#NUM!`.

### Top N Tricks
- **Second highest value:** `=LARGE(B2:B11,2)`
- **Total of the top 3:** `=SUM(LARGE(B2:B11,{1,2,3}))`
- **Highlight the top 3:** select the range > Conditional Formatting > Top/Bottom Rules > Top 10 Items > change 10 to 3.

---

## 7. More Rounding Tools

| Formula | Result | Meaning |
|---------|--------|---------|
| `=MROUND(17,5)` | 15 | Nearest multiple of 5 |
| `=CEILING(17,5)` | 20 | Up to the next multiple of 5 |
| `=FLOOR(17,5)` | 15 | Down to the previous multiple of 5 |
| `=EVEN(5)` | 6 | Up to the next even number |
| `=ODD(4)` | 5 | Up to the next odd number |

Useful for prices, time slots and packaging sizes.

---

## 8. Shortcuts

| Shortcut | Action |
|----------|--------|
| F9 | Recalculate now |
| Shift + F9 | Calculate the active sheet only |
| Ctrl + Alt + F9 | Recalculate everything |
| Ctrl + Alt + V, then V | Freeze formulas as values |
| Shift + F3 | Insert Function dialog |
| Ctrl + A | Function Arguments dialog (after typing the function name and `(`) |
| Alt + H + 0 | Increase decimal (display only) |
| Alt + H + 9 | Decrease decimal (display only) |

---

## 9. Interview Questions

- **ROUND vs the decimal buttons?** Alt + H + 9 only changes how the number **looks**. ROUND changes the **real value**.
- **INT vs TRUNC?** Same for positive numbers. For -5.5, INT gives -6 and TRUNC gives -5.
- **Why do random numbers change?** They are volatile. Any edit or F9 recalculates them. Use Paste Values to freeze.
- **How do you find the second highest value?** `=LARGE(range,2)`. The second lowest is `=SMALL(range,2)`.

---

## 10. Cheat Sheet

| Group | Functions |
|-------|-----------|
| Random | RAND, RANDBETWEEN, RANDARRAY |
| Round | ROUND, ROUNDUP, ROUNDDOWN |
| Round to a multiple | MROUND, CEILING, FLOOR, EVEN, ODD |
| Cut decimals | INT, TRUNC |
| Position in a list | LARGE, SMALL, MAX, MIN, RANK |

---

## Practice Sheet

The practice sheet has one table per function: Rand (0 to 1), RANDBETWEEN, RANDARRAY, ROUND, ROUNDUP, ROUNDDOWN, INT / TRUNC, LARGE and SMALL. In the LARGE and SMALL tables, the top values are highlighted with Conditional Formatting.

---

## Key Takeaway

ROUND changes the real value, formatting only changes the look. And `LARGE(range,2)` finds the second highest value in one formula.
