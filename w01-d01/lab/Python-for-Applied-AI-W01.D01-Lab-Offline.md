# Python for Applied AI — Day 01 · Extended

## Lab 01 Extended — running Python offline

**uv, VS Code and Jupyter on your own machine. The same code as Colab, with no internet.**

| | |
|---|---|
| Name | |
| Trade | AI for Everyone — Python track |
| Session / batch | Week 01, Day 01 |
| Date | 08 September 2026 |

> **Do Lab 01 first.** This sheet assumes your Colab notebook is working and your two labs run. Here you set the same thing up on your own machine.

> **The rule for this track:** type it yourself first, ask the assistant second. No pasting.

---

## What you hand in next session

1. A terminal showing `uv --version`.
2. A project folder called `openchat` with `pyproject.toml` and `.venv` in it.
3. `app.py` running with `uv run`, printing the same output as your Colab notebook.
4. `day01.ipynb` running in VS Code with the `.venv` kernel selected, saved with its output.
5. An export of that notebook as PDF or HTML.

**Time needed:** 45 to 90 minutes the first time, depending on your internet. After that, a new project takes two minutes.

---

## Part A · Why bother, when Colab works?

Colab is the fastest way to start and you will keep using it. But it lives on Google's computer, and that is a problem the first time you have no internet, a client's file that must not leave your laptop, or a script that has to run every morning at eight.

| | Colab | Your own machine |
|---|---|---|
| Internet needed | Yes, always | Only to install things the first time |
| Setup time | None | 45 minutes, once |
| Your client's private file | Uploaded to Google | Never leaves your laptop |
| Runs while you sleep | No, the session closes | Yes |
| Install any package | Every session, again | Once, and it stays |
| Good for | Learning, sharing, demos | Real client work |

> **You need both.** Colab for class and for showing people. Your own machine for work you are paid for.

### About the editor

We use **VS Code**. Two other editors you will hear about — **Cursor** and **Antigravity** — are built on VS Code, so every instruction on this sheet works in them too; only the AI panel differs. Pick one and stay with it for now.

There is a Colab extension for VS Code, but it still connects to Google over the internet. That is not offline. What follows is genuinely offline once installed.

---

## Part B · Install uv

**uv** installs Python for you and manages your projects. One tool instead of four.

Official instructions — check these, they change: **https://docs.astral.sh/uv/getting-started/installation/**

**Windows** — open PowerShell and run:

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

**macOS or Linux** — open Terminal and run:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

### Then, before anything else

- [ ] **Close the terminal completely and open a new one.** The installer adds uv to your PATH, and an already-open window does not know about it.
- [ ] Check it worked:

```bash
uv --version
```

**What version did it print?** _______________________________________

> If you get *command not found* or *not recognised*, you almost certainly skipped the close-and-reopen step. Do that first, before anything else.

---

## Part C · Install Python with uv

Guide: **https://docs.astral.sh/uv/guides/install-python/**

```bash
uv python install 3.13
```

- [ ] Installed 3.13
- [ ] Checked what uv can see:

```bash
uv python list
```

**Which versions appeared?** _______________________________________

> **Which version should you use?** 3.13 is the safe choice today — every library supports it. 3.14 is fine too. Do not reach for the newest release the week it appears; libraries take months to catch up, and a beginner cannot tell a library problem from their own mistake.

---

## Part D · Create your first project

### 1 · Go where you want it to live

```bash
cd Desktop
```

Use whatever suits you — `Documents`, a folder on your `E:` drive, anywhere you will find it again.

**Where did you put it?** _______________________________________

### 2 · Create the project

```bash
uv init openchat --python 3.13
cd openchat
```

**What files did uv make?** Look in the folder and write them down:

_______________________________________________________________________

| File | What it is |
|---|---|
| `pyproject.toml` | The project's identity card: its name, its Python version, its packages |
| `.python-version` | Which Python this project uses, so it does not matter what else is on your machine |
| `main.py` | A starter file with a hello-world in it |
| `README.md` | Where you describe the project |
| `uv.lock` | Appears later — the exact versions installed, so it works the same on another machine |
| `.venv` | Appears later — this project's own private Python. Never edit anything inside it |

### 3 · Create the environment

```bash
uv venv
```

**Activating it** (optional, but useful — see the note below):

| Your system | Command |
|---|---|
| Windows PowerShell | `.venv\Scripts\Activate.ps1` |
| Windows CMD | `.venv\Scripts\activate.bat` |
| macOS / Linux | `source .venv/bin/activate` |

- [ ] The prompt now shows `(openchat)` at the front

> **You do not have to activate.** Anything you run with `uv run` uses the project's own Python automatically. Activating is just convenient when you want to type `python` directly.

> **PowerShell refuses to activate?** Run `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` and try again. That setting lasts only for this window.

### 4 · Add Jupyter support

```bash
uv add ipykernel 
```

- [ ] Installed
- [ ] `pyproject.toml` now lists `ipykernel` under dependencies — open it and check

**What else changed after `uv add`?** _______________________________________

---

## Part E · Open it in VS Code

```bash
code .
```

The dot means *this folder*. If `code` is not recognised, open VS Code first, then **File → Open Folder** and choose `openchat`.

### Install two extensions

Click the squares icon in the left bar and search for each:

- [ ] **Python** (by Microsoft)
- [ ] **Jupyter** (by Microsoft)
- [ ] Optional: an icon theme, so file types are easier to spot at a glance

---

## Part F · Run a Python script offline

### 1 · Make the file

Right-click in the file list → **New File** → name it `app.py`.

### 2 · Type this in (do not paste)

```bash
uv add ollama
```

```python
from ollama import chat


response = chat(
    model='gemma3:1b',
    messages=[{'role': 'user', 'content': 'Hello!'}],
)

print(response.message.content)
```

### 3 · Open the terminal inside VS Code

Press **Ctrl + `** (the key above Tab). On a Mac it is the same key.

### 4 · Run it

```bash
uv run app.py
```

**What appeared in the terminal?**

_______________________________________________________________________

**Was it identical to what Colab printed in Lab 01?** _______________

> That sameness is the point. The same code, the same output, no internet.

---

## Part G · Jupyter inside VS Code — Colab, offline

### 1 · Make the notebook

New File → name it `day01.ipynb`. VS Code opens it as a notebook, with cells.

### 2 · Choose the kernel

Top right, click **Select Kernel** → **Python Environments** → the one showing `.venv` inside your `openchat` folder.

- [ ] Kernel selected, and it says `.venv` — **not** a system Python

**Which kernel did you pick?** _______________________________________

> If no kernel appears, `ipykernel` is missing. Go back to Part D step 4.

### 3 · Add a heading

Add a **Markdown** cell and type:

```markdown
# Day 01 — Python for Applied AI
My first offline notebook. Same code as Colab, running on my own machine.
```

### 4 · Add a code cell and type the name-cleaner

```python
names = ["  usman ali ", "SARA AHMAD", "bilal  ", " Ahmad Khan"]

for raw in names:
    clean = raw.strip().title()
    print(clean)
```

### 5 · Run it

**Shift + Enter**, exactly as in Colab.

**What did it print?**

_______________________________________________________________________

### 6 · Save, share, prove it

- [ ] Saved the notebook — **the output is saved with it**, so anyone opening the file sees your results
- [ ] Exported it: **… → Export → PDF** or **HTML** (PDF may ask you to install one extra piece; HTML always works)
- [ ] Uploaded the same `.ipynb` to Colab and ran it there — it works unchanged

**Which export did you produce?** _______________________________________

> A notebook is one file. It runs in VS Code, it runs in Colab, and it exports to a PDF you can send to somebody. That is why this format is worth learning.

---

## Part H · When the offline setup fights you

| What you see | What it usually means | What to do |
|---|---|---|
| `uv: command not found` | The terminal was open before uv was installed | Close every terminal, open a new one |
| PowerShell: *running scripts is disabled* | Windows is blocking the activate script | `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` |
| `code .` not recognised | VS Code is not on your PATH | Open VS Code and use File → Open Folder instead |
| No kernel to select in the notebook | `ipykernel` not installed in this project | `uv add ipykernel`, then reload VS Code |
| Notebook runs the wrong Python | A system kernel was selected, not the project one | Click the kernel name, pick the one with `.venv` in the path |
| `ModuleNotFoundError` for something you installed | You installed it outside this project | `cd` into the project folder and use `uv add` |
| Downloads keep failing | Connection dropped mid-install | Run the same command again — uv resumes rather than starting over |

**Which of these hit you, and what fixed it?**

_______________________________________________________________________

---

## Before you submit

- [ ] Name, trade and session at the top
- [ ] `uv --version` prints a version
- [ ] Python 3.13 installed through uv
- [ ] `openchat` project created, with `pyproject.toml` and `.venv`
- [ ] `ipykernel` added and listed in `pyproject.toml`
- [ ] `uv run app.py` prints the same output as Colab
- [ ] `day01.ipynb` runs in VS Code with the `.venv` kernel selected
- [ ] Notebook saved with its output, and exported to PDF or HTML
- [ ] The same `.ipynb` opened and run in Colab

---

## Done properly means

- Your notebook shows `.venv` as its kernel. If it shows a system Python, the project is not really self-contained and it will break later.
- `uv run app.py` printed exactly what Colab printed. Same code, same answer, no internet.
- You wrote down which commands failed and what fixed them. Next time you set this up it takes ten minutes, and only because of those notes.
- You can now do the same work two ways, and you can say which one a job needs.

> Every project from here on starts the same way: `uv init`, `cd`, `uv add` what you need. Learn these four commands properly now and you will use them for years.
