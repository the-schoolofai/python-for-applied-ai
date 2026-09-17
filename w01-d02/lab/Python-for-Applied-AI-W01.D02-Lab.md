# Python for Applied AI — Day 2

## Lab and homework worksheet

**Variables, types, strings and f-strings**

| | |
|---|---|
| Name | |
| Trade | AI for Everyone — Python track |
| Session / batch | Week 02, Day 02 |
| Date | 09 September 2026 |

> **The rule stands:** type it yourself first, ask the assistant second, retype anything you accept. Nothing on this sheet is pasted.

---

## What you hand in next session

1. A variables-and-types notebook, including one TypeError you caused and fixed.
2. Your own messy list, cleaned.
3. A working message generator, run twice with different data.
4. The same message rewritten as an AI prompt.
5. A small CSV or spreadsheet (optional).

**Time needed:** 60 minutes of lab in class, about 20 minutes at home.

---

## Part A · Lab 1 — variables and types

### A1 · Describe one order

Five variables. Name them properly — lower case, underscores, meaningful.

| What it holds | Your variable name | The value you used | Type it should be |
|---|---|---|---|
| Client name | | | |
| City | | | |
| Item | | | |
| Quantity | | | |
| Unit price | | | |

### A2 · Calculate

```python
total = quantity * unit_price
print(total)
```

**What printed?** ___________________________________________

**Now change the quantity and run it again. What printed?** ___________________________________________

### A3 · Cause a TypeError on purpose

Put the price in quotes, like `unit_price = "450"`, and run the calculation again.

| | |
|---|---|
| The last line of the error | |
| What it meant, in your own words | |
| The line that fixed it | |

> Careful: if you put the **quantity** in quotes instead, you may get no error at all — just a wrong answer. Try it and see what `"3" * 2` gives you.

**What did `"3" * 2` print?** _______________________________

### A4 · Check every type

```python
print(type(client_name), type(quantity), type(unit_price))
```

**Is anything the wrong type?** ___________________________________________

**Should a phone number or product code be text or a number, and why?**

_______________________________________________________________________

---

## Part B · Lab 2 — clean your own messy list

Use the list you brought in.

```python
raw = "  put your messy list here, separated by commas  "

parts = raw.split(",")

for p in parts:
    clean = p.strip().title().replace("  ", " ")
    print(clean)
```

**How many items came out?** _____________

**Anything that came out wrong?** ___________________________________________

### Try each method on its own

| Change | What happened |
|---|---|
| Remove `.strip()` | |
| Replace `.title()` with `.lower()` | |
| Remove `.replace("  ", " ")` | |
| Put a comma inside one of the names | |

**The last row is a real problem. What would you do about it?**

_______________________________________________________________________

---

## Part C · Lab 3 — the message generator

### C1 · Set your variables

| | Value |
|---|---|
| client_name | |
| city | |
| product | |
| quantity | |
| unit_price | |
| delivery_day | |

### C2 · Calculate and format

```python
total = quantity * unit_price
print(f"Rs {total:,.2f}")
```

**What printed?** ___________________________________________

### C3 · Write the message

One f-string, several lines, using **every** variable. Write it here first, then type it.

```python
message = f"""
_______________________________________________________________________

_______________________________________________________________________

_______________________________________________________________________
"""
print(message)
```

- [ ] It reads like something you would actually send
- [ ] Every variable is used
- [ ] The total is formatted with a comma and two decimals

### C4 · Change one variable only

Change the client name and the quantity. **Do not touch anything else.**

- [ ] It ran
- [ ] The message is correct for the new client
- [ ] I changed nothing except the variables

**How long would this have taken by hand, for forty clients?**

_______________________________________________________________________

### C5 · Now make it a prompt

Rewrite the same thing as a prompt for an AI tool.

```python
prompt = f"""You are {role} writing to {client_name}.
_______________________________________________________________________

_______________________________________________________________________
"""
print(prompt)
```

**Paste the printed prompt into Claude or ChatGPT. Was the output usable?**

_______________________________________________________________________

---

## Part D · The four mistakes — tick each one you made today

- [ ] Forgot the `f` before the quotes, and the braces printed literally
- [ ] Quote inside a quote ended the string early
- [ ] A number stayed as text and the maths went wrong without an error
- [ ] Reused one variable name for two different things

**Which one cost you the most time?**

_______________________________________________________________________

---

## Part E · Homework — twenty minutes

1. **Rebuild the generator** from scratch in a new notebook, no slides, no sheet. Note where you stopped and thought.
2. **Three formats:** print one money amount, one percentage, and two columns that line up. Screenshot it.
3. **Bring a file:** a small CSV or spreadsheet from your work — orders, attendance, stock, contacts. Ten to a hundred rows.

**Where I got stuck rebuilding:**

_______________________________________________________________________

**The file I am bringing:** ________________________________________

---

## Before you submit

- [ ] Name, trade and session at the top
- [ ] Five variables named properly, with types checked
- [ ] One TypeError caused, understood and fixed
- [ ] `"3" * 2` tried and the result written down
- [ ] Own messy list cleaned, four variations tried
- [ ] Message generator working, run twice, changing only variables
- [ ] Message rewritten as a prompt and tested in a real AI tool
- [ ] Three number formats produced
- [ ] A file ready for Day 3

---

## For the trainer

**What good work looks like**

- A1 names are `client_name` and `unit_price`, not `a`, `n1`, `x`. Hand back anything with single-letter names — it takes thirty seconds now and saves months.
- A3 has the real error text copied, and the fix uses a conversion rather than simply removing the quotes. Both work; only one teaches the lesson.
- The `"3" * 2` answer is written as `33`. Trainees who wrote `6` guessed instead of running it.
- C4 is honest about changing nothing but the variables. The point of the exercise is that the message logic never moves.
- C5 was actually pasted into a tool and judged. That step is what connects this track to the main course.

**Common failures and the fix**

| Problem | What to do |
|---|---|
| Wrote `f` only on the first line of a triple-quoted string | Correct — that is right. The f goes once, before the opening triple quote. |
| Message hard-codes the client name inside the text | The whole point is gone. Ask them to change the variable and watch nothing happen. |
| Used `+` to join everything instead of an f-string | It works, and it breaks the moment a number appears. Show the TypeError, then convert it. |
| No output written on the sheet | The written output is the evidence they ran it. Send it back. |
| Asked the assistant to write C3 whole | Sit with them for two minutes. Usually they were stuck on triple quotes, not unwilling. |

**On the comma-inside-a-name row in Part B.** This has no clean fix with `split(",")`, and that is the honest answer. Say so: it is exactly why proper CSV reading exists, which is Day 3's first topic. Leaving a real limitation visible is better teaching than pretending the method is universal.

**Quick marking scale**

| | |
|---|---|
| **Complete** | Types checked, TypeError understood, list cleaned, generator run twice, prompt tested in a tool |
| **Partial** | Generator works but variables hard-coded, or the prompt step skipped |
| **Not done** | Rebuild tonight — Day 3 loops over a file and assumes f-strings are comfortable |

**Opening next session:** ask one trainee to run their generator on the projector and change the client name live. Then collect the files. Day 3's first lab reads a real one, and it works best when the data belongs to somebody in the room.
