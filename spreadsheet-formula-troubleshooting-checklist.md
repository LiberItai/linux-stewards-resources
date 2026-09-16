# Spreadsheet formula & data troubleshooting checklist

A plain-English, step-by-step guide for small businesses and individuals when an
Excel or Google Sheets file gives wrong results, shows errors, or behaves oddly.
Work through the steps in order — each one is safe and reversible. If you reach
the end without a fix, the notes you have collected will make professional help
much faster and cheaper.

## Before you change anything

- [ ] Save a copy of the file under a new name before editing, so you can always go back.
- [ ] Note exactly which cell shows the error and the exact text (for example `#DIV/0!`, `#N/A`, `#REF!`, `#VALUE!`, `#NAME?`).
- [ ] Write down what the formula is supposed to do in one sentence — the expected result.

## Common error messages and what they usually mean

- [ ] `#DIV/0!` — the formula is dividing by zero or by an empty cell. Check the divisor cell actually has a number.
- [ ] `#VALUE!` — the formula is using the wrong type of data (text where a number is expected, or a date treated as text).
- [ ] `#REF!` — the formula points to a cell or sheet that was deleted or moved. Check the referenced range.
- [ ] `#NAME?` — a function or range name is misspelled, or the function is not available in your version.
- [ ] `#N/A` — a lookup did not find a match (for example `VLOOKUP` or `XLOOKUP` with no matching value).
- [ ] `#SPILL!` (Excel) — a result cannot spill because another cell is in the way. Clear the blocking cells.

## Fix the inputs first

- [ ] Check for leading/trailing spaces in text cells — they break lookups and comparisons.
- [ ] Confirm numbers are stored as numbers, not text (a text number often sits left-aligned and breaks sums).
- [ ] Check for merged cells — they frequently break sorting, filtering and formulas.
- [ ] Look for hidden rows/columns that may be feeding a formula with unexpected data.

## Fix the formula

- [ ] Check the cell references are correct (absolute `$A$1` vs relative `A1` matters when you copy down).
- [ ] Use Excel's "Trace Precedents"/"Trace Dependents", or Google Sheets' "Show formula" view, to see what feeds the cell.
- [ ] For lookups, confirm the lookup value exists exactly in the search column, with no extra spaces or format mismatch.
- [ ] Break a long formula into smaller pieces in helper cells, test each part, then rebuild.

## After you fix it

- [ ] Re-check a few known-good examples to confirm the result is right.
- [ ] Remove helper cells you no longer need, and tidy any leftover blocking cells.
- [ ] Keep a small note in the file or alongside it describing what the formula is meant to do.

## When to stop and get help

- [ ] Stop if a fix feels risky or if you are about to overwrite the only good copy.
- [ ] Summarise the exact error text, what the formula should do, and what you already tried.
- [ ] For remote help worldwide: [linuxstewards.com/services](https://www.linuxstewards.com/services)

Linux Stewards provides remote spreadsheet, data, website, Windows/Mac and Linux
help for small businesses and individuals. Small jobs are genuinely welcome —
entry spreadsheet fixes start from £19.
