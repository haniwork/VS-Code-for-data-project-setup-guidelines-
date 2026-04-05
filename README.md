# VS Code for Data & AI Projects: Comprehensive Setup Guide

This guide outlines the professional standard for setting up Visual Studio Code (VS Code) for Data Science and AI Engineering. By moving beyond standalone notebooks, you ensure your work is reproducible, version-controlled, and production-ready.

---

## 💡 Why VS Code + GitHub instead of standalone Jupyter?

While Jupyter Notebooks are excellent for rapid exploration, they often become a "black box" of unorganized code. Pairing VS Code with GitHub transforms your workflow into a professional engineering standard.

### The Version Control Problem
Standard Jupyter Notebooks are stored as large **JSON files**. When you change a single cell, the underlying file structure changes drastically, making "Diffs" (seeing what changed) nearly impossible to read in a browser. 

**VS Code + GitHub solves this by:**
* **Native Diffing:** VS Code provides a "Jupyter Rendered Diff" that shows exactly which code lines changed, filtering out the messy JSON metadata.
* **Modularization:** VS Code makes it easy to move stable functions from `.ipynb` files into `.py` modules, which are significantly easier to version control.
* **Collaboration:** GitHub integration allows for seamless Pull Requests and "Time Travel" (reverting to a stable version of your model).

| Feature | Jupyter Notebook (Web) | VS Code + GitHub |
| :--- | :--- | :--- |
| **Version Control** | JSON diffs are unreadable. | Clean, visual diffs and easy branching. |
| **Debugging** | Basic print-statements. | Full visual debugger with variable watch. |
| **Automation** | Manual execution. | Integrated CI/CD via GitHub Actions. |
| **Production** | Difficult to deploy. | Seamless transition from notebook to script. |

---

## 🐍 Python & Environment Setup (Conda)

Using isolated environments prevents dependency conflicts—a common headache in AI projects.

### 1. Create and Activate Environment
You can create a new environment or use an existing one. To create a new one:
```bash
conda create -n venv_name_example python=3.11 -y
conda activate venv_name_example
```

### 2. Connect to VS Code
1. Open the **Command Palette** (`Ctrl + Shift + P` / `Cmd + Shift + P`).
2. Type and select: **Python: Select Interpreter**.
3. Choose `venv_name_example` from the list. If you are using an existing environment not listed, select **Enter interpreter path...** and point to the Python executable.

---

## 🛠️ Managing Libraries & Dependencies

Once your environment is active, you need to install the tools required for data analysis and AI development.

### 1. Essential Core Libraries
Before running notebooks, you must install the Jupyter kernel and basic data stacks within your environment:
```bash
pip install jupyter ipykernel pandas numpy matplotlib
```

---

## 2. Installing via pip

To install a specific library (e.g., Scikit-Learn or PyTorch), use the `pip install` command:
```
pip install scikit-learn
```

---

## 3. Bulk Installation using requirements.txt

In professional projects, dependencies are usually listed in a `requirements.txt` file. This ensures everyone on your team uses the exact same versions.

To install everything listed in a project's requirement file, run:

Bash
```
pip install -r requirements.txt
Pro Tip: To create your own requirements file based on what's currently installed in your environment, use:
pip freeze > requirements.txt
```
---

## 4. Verifying Your Installation

To see a list of all libraries currently installed in your active environment:

Bash
```
pip list
```

### Where to place this in your full document:
I recommend inserting this block **between** "Python & Environment Setup" and "Essential Extensions". This creates a logical flow: 
1. Create Env 
2. **Install Libraries (This section)** 3. Setup Editor Extensions 
4. Start Coding.

---

## 📦 Essential Extensions
Install these via the Extensions view (`Ctrl + Shift + X`):

* **Python & Jupyter:** The core engine for running scripts and notebooks.
* **GitHub Copilot:** AI-powered pair programming.
* **Ruff:** An extremely fast linter and formatter.
* **GitLens:** See who changed what line and when (blame annotations).

---

## ⚡ Interactive Python (The Best of Both Worlds)
You don't need a `.ipynb` file to run code iteratively.

1. In any `.py` file, **highlight** a block of code.
2. Press `Shift + Enter`.
3. VS Code opens an **Interactive Window** on the side. You get the benefit of a notebook (visualizing dataframes and plots) while keeping your code in a clean, versionable script.

---

## 🌿 Version Control: Working with Git in VS Code
VS Code provides a visual **Source Control** tab (`Ctrl + Shift + G`) that simplifies the Git lifecycle.

### 1. The Workflow: Stage, Commit, Push
* **Staging:** Click the **+** icon next to a file to prepare it for a snapshot.
* **Committing:** Type a descriptive message (e.g., `feat: add data cleaning module`) and click **Commit**.
* **Pushing:** Click **Sync Changes** to upload your work to GitHub.

### 2. Visualizing Diffs
Before committing, click a file in the Source Control side-bar. VS Code opens a **Side-by-Side Diff**. This is your final sanity check to ensure you aren't committing temporary "test" code or sensitive API keys.

---

## 🎨 UI, Styling & Auto-Formatting

### Theme & Icons
* **Color Theme:** Atom One Dark or Dracula.
* **File Icons:** Material Icon Theme.

### Auto-Formatting (The "No-Effort" Way)
Stop worrying about code style. Let **Ruff** handle it every time you save. Add this to your `settings.json` (Open with `Ctrl + ,` and click the "Open Settings JSON" icon):

```json
{
  "editor.formatOnSave": true,
  "[python]": {
    "editor.defaultFormatter": "charliermarsh.ruff",
    "editor.codeActionsOnSave": {
      "source.fixAll.ruff": "always",
      "source.organizeImports.ruff": "always"
    }
  },
  "material-icon-theme.folders.associations": {
    "env": "environment",
    "references": "docs",
    "modeling": "generator",
    "data": "folder-database",
    "notebooks": "folder-jupyter"
  }
}
