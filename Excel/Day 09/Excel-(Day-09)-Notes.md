# Day 09: Date and Time Formulas

## 1. Date and Time Basics

- Excel stores a **date as a serial number** (1 = 1 Jan 1900). Formatting makes it look like a date.
- **Time is a fraction of a day.** 0.5 = 12:00 PM, 0.25 = 6:00 AM.
- **Date parts:** Month, Day, Year make a date (format `MM-DD-YYYY`).
- **Time parts:** Hour, Minute, Second and AM/PM make a time.

---

## 2. TODAY and NOW

| Formula | Result |
|---------|--------|
| `=TODAY()` | Current date (live) |
| `=NOW()` | Current date and time (live) |
| `=TODAY()+7` | 7 days from today |
| `=NOW()+7` | 7 **days** later |
| `=NOW()+7/24` | 7 **hours** later |

- **Formulas update every day.** Shortcut keys insert a **fixed** value that never updates.
- Adding 1 adds a whole day, so use `/24` for hours.
- Show the time part: `=TEXT(NOW()+(7/24),"h:mm:ss AM/PM")`.

---

## 3. Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl + ; | Insert today's date (fixed) |
| Ctrl + Shift + ; | Insert current time (fixed) |
| Ctrl + Shift + # | Date format |
| Ctrl + Shift + @ | Time format |
| Ctrl + 1 | Format Cells > Custom |
| F9 | Recalculate TODAY / NOW |

**Date and time together:** press Ctrl + ; then a Space, then Ctrl + Shift + ;.

| | Shortcut | Formula |
|--|----------|---------|
| Current date | Ctrl + ; | `=TODAY()` |
| Current time | Ctrl + Shift + ; | `=NOW()` |
| Updates daily? | No | Yes |

---

## 4. TEXT with Dates and Time

| Formula | Result |
|---------|--------|
| `=TEXT(TODAY(),"mm-dd-yyyy")` | 10-18-2026 |
| `=TEXT(NOW(),"h:mm AM/PM")` | 4:33 PM |
| `=TEXT(B6,"ddd")` | Mon (B6 = 14-05-2012) |
| `=TEXT(A1,"AM/PM")` | AM |
| `=TEXT(TIME(C33,D33,E33),"hh:mm:ss AM/PM")` | 5:10:04 PM |

- An `mm` next to hours means **minutes**. Elsewhere it means **months**.
- The result of TEXT is **text**, not a real date.

### Date Format Codes

Example date: 18 October 2026

| Code | Result |
|------|--------|
| `dd` | 18 |
| `ddd` | Sun |
| `dddd` | Sunday |
| `mmm` | Oct |
| `mmmm` | October |
| `yyyy` | 2026 |

---

## 5. DAYS and NETWORKDAYS

C33 = `10-04-2026` (Friday), D33 = `15-04-2026` (Wednesday)

| Formula | Result |
|---------|--------|
| `=DAYS(D33,C33)` | 5 (end date comes first) |
| `=NETWORKDAYS(C33,D33)` | 4 (skips Saturday and Sunday) |
| `=NETWORKDAYS(C33,D33,$A$54:$A$55)` | Skips weekends and the holiday list |

- **DAYS** counts every day. **NETWORKDAYS** counts only working days (Fri, Mon, Tue, Wed = 4).
- Lock the holiday range with `$` when copying the formula.

### NETWORKDAYS.INTL (custom weekend)

**Syntax:** `=NETWORKDAYS.INTL(start, end, weekend, holidays)`

- The weekend is a **7-digit string** for Monday to Sunday: `1` = day off, `0` = working day.
- `"0000011"` = Saturday and Sunday off.
- `"1010000"` = Monday and Wednesday off.
- Full formula: `=NETWORKDAYS.INTL(B54,C54,"1010000",$A$54:$A$55)`
- Weekend codes also work: 1 = Sat + Sun (default), 2 = Sun + Mon, 11 = Sunday only.

### DAYS360

- Every month counts as 30 days, so a year has 360 days.
- **Syntax:** `=DAYS360(start, end, method)`
- Method `0` or FALSE = **US method** (default). Method `1` or TRUE = **European method**.

---

## 6. WORKDAY (Find a Target Date)

| Formula | Result |
|---------|--------|
| `=WORKDAY(DATE(2026,10,28),7)` | 06-Nov-2026 |
| `=WORKDAY(B33,30)` | 30 working days later |
| `=WORKDAY(B33,-5)` | 5 working days back |
| `=WORKDAY(B33,30,$A$54:$A$55)` | Also skips holidays |
| `=WORKDAY.INTL(B33,30,"0000011")` | Custom weekend |

- **NETWORKDAYS:** working days **between** two dates.
- **WORKDAY:** finds the **target date** in the future or past. Used for deadlines, target dates and resignation dates.
- **Example (30-day notice):** start date + 30 = 30 **calendar** days. `WORKDAY(start,30)` = 30 **working** days (weekends not included).
- Format the result as a date (Ctrl + Shift + #), or you will see a serial number.

---

## 7. EDATE and EOMONTH

B33 = `18-Oct-2026`

| Formula | Result |
|---------|--------|
| `=EDATE(B33,2)` | 18-Dec-2026 |
| `=EDATE(B33,-1)` | 18-Sep-2026 |
| `=EOMONTH(B33,0)` | 31-Oct-2026 |
| `=EOMONTH(B33,2)` | 31-Dec-2026 |

- **EDATE** (End Date): calculates a **due date**. Example: you borrow Rs. 5000 on 18-Oct and return it after 2 months, so the due date is 18-Dec. It counts real months, not `2 x 30 = 60` days.
- **EOMONTH** (End of Month): always returns the **last day** of the month. With `0` months you get the end of the current month. Used in trackers.

---

## 8. DATEDIF and YEARFRAC

A1 = `04-11-2004` (date of birth), B1 = `18-10-2026` (today)

| Formula | Result |
|---------|--------|
| `=DATEDIF(A1,B1,"Y")` | 21 years (age) |
| `=DATEDIF(A1,B1,"M")` | 263 months |
| `=DATEDIF(A1,B1,"YM")` | 11 months (ignoring years) |
| `=DATEDIF(A1,B1,"D")` | 8018 days |
| `=YEARFRAC(A1,B1)` | 21.9555... (year fraction) |

- DATEDIF is a **hidden function**, so Excel shows no tooltip while typing.
- The start date must be earlier than the end date, or you get `#NUM!`.

---

## 9. WEEKDAY and WEEKNUM

B33 = `10-04-2026` (Friday)

| Formula | Result |
|---------|--------|
| `=WEEKDAY(B33)` | 6 (Sunday = 1) |
| `=WEEKDAY(B33,2)` | 5 (Monday = 1) |
| `=WEEKNUM(B33)` | 15 (week of the year) |
| `=ISOWEEKNUM(B33)` | 15 (ISO week) |
| `=TEXT(B33,"dddd")` | Friday |

- WEEKDAY counts the day of the week. Sunday is the first day by default.
- WEEKNUM gives the week of the year, like week 15.

---

## 10. Convert Text to Date and Time

| Formula | Result |
|---------|--------|
| `=DATEVALUE("09-Apr-2026")` | 46121 (format as a date to see it) |
| `=TIMEVALUE("10:30 AM")` | 0.4375 (format as a time to see it) |
| `=DATE(2026,10,18)` | 18-Oct-2026 |
| `=TIME(17,10,4)` | 5:10:04 PM |

- **DATEVALUE** and **TIMEVALUE** turn **text** into real numbers.
- **DATE** and **TIME** build a value from separate numbers.

### Pick Out the Parts

| Formula | Result |
|---------|--------|
| `=DAY(B33)` | 10 |
| `=MONTH(B33)` | 4 |
| `=YEAR(B33)` | 2026 |
| `=HOUR(B2)` | 17 |
| `=MINUTE(B2)` | 10 |
| `=SECOND(B2)` | 4 |

B2 = 5:10:04 PM. HOUR uses the 24-hour clock, so 5 PM is 17.

---

## 11. Cheat Sheet

| Group | Functions |
|-------|-----------|
| Live | TODAY, NOW |
| Build | DATE, TIME |
| Pick parts | YEAR, MONTH, DAY, HOUR, MINUTE, SECOND |
| Day and week | WEEKDAY, WEEKNUM, ISOWEEKNUM |
| Differences | DAYS, DATEDIF, YEARFRAC, DAYS360 |
| Working days | NETWORKDAYS, NETWORKDAYS.INTL, WORKDAY, WORKDAY.INTL |
| Move and convert | EDATE, EOMONTH, DATEVALUE, TIMEVALUE, TEXT |

---

## Key Takeaway

Formulas keep dates live, shortcuts freeze them, and WORKDAY, EDATE and DATEDIF turn dates into deadlines, due dates and ages.
