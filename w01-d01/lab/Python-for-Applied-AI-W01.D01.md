# Python for Applied AI — Day 01

## Lab and homework worksheet

**Your first notebook, your first errors, your first useful script**

| | |
|---|---|
| Name | |
| Trade | AI for Everyone — Python track |
| Session / batch | Week 01, Day 01 |
| Date | 08 September 2026 |

> **The rule for this track:** type it yourself first, ask the assistant second. Everything on this sheet is typed by hand. No pasting today.

---

## What you hand in next session

1. A Google Colab notebook saved in your own Drive, with labs in it.
2. Three errors you caused on purpose, with what each one told you.
3. Your own version of the name-cleaning script.
4. A messy list from your real work, ready for next session.

**Time needed:** 65 minutes in class, about 20 minutes at home.

---

## Part A · Setup — five minutes

- [ ] Opened **colab.research.google.com**
- [ ] Signed in with the Google account from Week 01
- [ ] Clicked **New notebook**
- [ ] Renamed it: `Python Day 01 — [your name]`
- [ ] Found it in Drive, under the folder **Colab Notebooks**

**If something failed, write what happened:**

_______________________________________________________________________

> Nothing is installed on your computer. If the power goes, your notebook is safe in Drive — you lose the last few minutes, not the work.

### Three things to know about Colab

| To do this | Do that |
|---|---|
| Run the cell you are in | Press **Shift + Enter** |
| Add a new cell | Click **+ Code** at the top |
| Start again cleanly | **Runtime → Restart**, then run your cells from the top |

---

## Part B · Lab 1 — your first notebook

Type each block into a **separate cell**. Press **Shift + Enter** to run a cell.

### Cell 1

```python
name = "Bilal"
city = "Lahore"

print("Hello,", name + "!", "Welcome from", city + "!")
```

**What did it print?**

_______________________________________________________________________

### Cell 2

```python
orders = [120, 340, 90, 560]

print("Order Summary")
print("--------------")
print("Total Orders:", len(orders))
print("Total Amount:", sum(orders))
print("Biggest Order:", max(orders))
```

**What did it print?**

_______________________________________________________________________

### Cell 3 — make it yours

Change the name, the city and the numbers to your own. Run it again.

**Your version printed:**

_______________________________________________________________________

### Name what you just used

| Word | What it means, in your own words |
|---|---|
| Variable (`name`, `city`) | |
| List (`orders`) | |
| Function (`print`, `len`, `sum`, `max`) | |

---

## Part C · Break it on purpose

This is the most important twenty minutes of the day. Cause each error deliberately.

**How to read an error:** the **last line** names the problem. The lines above it are the path Python took to get there.

| # | What you changed | The last line of the error | What it meant, in your words | How you fixed it |
|---|---|---|---|---|
| 1 | Deleted a quotation mark | | | |
| 2 | Misspelled a variable name | | | |
| 3 | `print("Total Orders:" + 120)` | | | |

**Which error was hardest to understand, and why?**

_______________________________________________________________________

> An error is Python telling you exactly where it got confused. It is information, not rejection.

---

## Part D · Lab 2 — something actually useful

Type this into a new cell:

```python
names = ["  ali khan ", "SARA AHMED", "bilal  ", " Ayesha Khan"]

for raw in names:
    clean = raw.strip().title()
    print(clean)
```

> **Watch the indentation.** The two lines under `for` must be pushed in. Colab does it for you when you press Enter after the colon — do not fight it.

**What did it print?**

_______________________________________________________________________

### Now change things and see what happens

| Change | What happened |
|---|---|
| Replace `.title()` with `.upper()` | |
| Remove `.strip()` | |
| Add your own messy name to the list | |
| Remove the indentation on the last line | |

**In one sentence — what does `.strip()` do?**

_______________________________________________________________________

**In one sentence — what does the `for` line do?**

_______________________________________________________________________

---

## Part E · When it will not run — check these five first

Work down the list before you ask anyone. Four out of five times, the problem is here.

| # | Check | What it looks like |
|---|---|---|
| 1 | A capital letter | `Print` instead of `print`, or `Orders` instead of `orders` |
| 2 | A missing quotation mark | The colours in the cell look wrong from that point on |
| 3 | A missing colon | Nothing after `for raw in names` |
| 4 | Indentation | The lines under `for` are not pushed in, or not pushed in equally |
| 5 | Cells run out of order | You ran Cell 2 before Cell 1. Run from the top |

**Which of these five caught you today?**

_______________________________________________________________________

---

## Part F · How to ask the assistant

You may ask for help **after** you have attempted it. Ask for an explanation, not for code.

**Use this shape:**
> I am learning Python. Here is my code: [paste your code]
> Here is the error: [paste the whole error]
> Explain why this happened in simple English. **Do not rewrite my code** — tell me what to change and I will type it.

**One question you asked today, and what you learned from the answer:**

_______________________________________________________________________

_______________________________________________________________________

---

## Part G · Homework — twenty minutes, not two hours

1. **Retype lab** from scratch in a new notebook, without looking at this sheet. Note where you got stuck.
2. **Cause three more errors** — different ones from Part C — and write down what each said.
3. **Bring a messy list**: real names, products, cities or items from your work, your family's business, or your phone contacts.

**Where I got stuck when retyping:**

_______________________________________________________________________

**The messy list I am bringing:**

_______________________________________________________________________

---

## Before you submit

- [ ] Name, trade and session at the top
- [ ] Notebook saved in Drive with your name in the title
- [ ] Lab typed by hand — nothing pasted
- [ ] Output written down for each cell
- [ ] Three deliberate errors recorded with their last lines
- [ ] Four changes tried in Lab 2, with what happened
- [ ] `.strip()` and `for` explained in your own words
- [ ] A messy list ready for next session

---

## Done properly means

- Your error table has the **real last line** copied exactly — something like `SyntaxError: unterminated string literal`, not "it broke".
- The plain-English column is yours: *"It expected a closing quote and did not find one."* If you can say it, you can fix it next time.
- Every row of the change table in Part D was actually run. Do not guess what would have happened.
- The question you asked in Part F was a **why** question, not a request for code.

> Twenty minutes a day beats four hours on a Sunday. Programming is a skill your hands learn, not only your head.
