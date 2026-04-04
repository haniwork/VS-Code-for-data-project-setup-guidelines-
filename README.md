# VS-Code-for-data-project-setup-guidelines-

# VS Code for Data & AI Projects

### A Comprehensive Setup Guide

---

## Introduction

Visual Studio Code (VS Code) is a free, powerful, and extensible IDE for modern development.

### Key Features

* Multi-language support
* Debugging tools
* Intelligent code completion
* Built-in Git integration
* Large extension marketplace

---

## Python Setup (Conda)

### Create Environment

```bash
conda create -n myenv python=3.11
```

### Activate Environment

```bash
conda activate myenv
```

---

## Command Palette

Open with:

* `Ctrl + Shift + P` (Windows/Linux)
* `Cmd + Shift + P` (Mac)

Use it to quickly access all VS Code commands.

---

## Workspace Setup

### Organize Projects

```
Repositories/
  ├── personal/
  └── work/
```

---

### Open Folder

* File → Open Folder

Or via terminal:

```bash
code .
```

Enable via:

```
Shell Command: Install 'code' command in PATH
```

---

### Save Workspace

* File → Save Workspace As

---

## Conda Environment in VS Code

1. Open Command Palette
2. Select: **Python: Select Interpreter**
3. Choose your Conda environment

---

## Installing Extensions

Open Extensions (`Ctrl + Shift + X`) and install:

* Python Extension Pack
* GitHub Copilot
* Ruff
* Path Intellisense
* GitHub Pull Requests
* Better Comments
* Material Icon Theme
* Atom One Dark Theme

---

## Styling VS Code

### Theme

* Color Theme: Atom One Dark
* File Icons: Material Icon Theme

---

### Custom Icons

```json
"material-icon-theme.folders.associations": {
  "env": "environment",
  "references": "docs",
  "modeling": "generator"
}
```

---

## Auto Formatting

Enable:

* Format on Save
* Ruff as default formatter

```json
"[python]": {
  "editor.formatOnType": true,
  "editor.defaultFormatter": "charliermarsh.ruff"
}
```

---

## Jupyter Notebooks

* Open `.ipynb` files directly
* Select correct Conda kernel

---

## Interactive Python

* Use `Shift + Enter` to run code interactively

---

### Set Notebook Root

```json
"jupyter.notebookFileRoot": "${workspaceFolder}/app"
```

---

## GitHub Integration

### Features

* Commit, push, pull inside VS Code
* Branch management
* View diffs visually

---

## Final Thoughts

Using VS Code with Conda provides a scalable and efficient setup for data science and AI workflows.
