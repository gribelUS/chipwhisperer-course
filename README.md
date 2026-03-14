# ChipWhisperer Course Environment

This repository contains the notebooks and environment setup for ChipWhisperer labs using:

- CW Nano
- CW Lite + CW305

The goal of this repository is to provide ready-to-run experiments with minimal setup.  
Students only need to clone **one repository** and choose either a **venv** or **Conda** environment.

This repository also contains a tracked copy of the official NewAE notebooks for reference.

---

# Repository Structure

```
chipwhisperer-course/
│
├── notebooks/
│   ├── cwnano/
│   └── cwlite_cw305/
│
├── support/
│   ├── cwnano/
│   └── cwlite_cw305/
│
├── env/
│   ├── requirements.txt
│   └── environment.yml
│
├── upstream/
│   └── chipwhisperer-jupyter/
│
└── README.md
```

| Folder | Purpose |
|--------|----------|
| notebooks | Student notebooks |
| support | Helper Python code |
| env | Environment definitions |
| upstream | Official ChipWhisperer notebooks (reference only) |

Students should work only inside `notebooks/`.

---

# Prerequisites

Install before starting:

- Git
- Python 3.9 – 3.11
- Optional: Miniconda or Anaconda

---

# Clone Repository

```
git clone https://github.com/gribelUS/chipwhisperer-course.git
cd chipwhisperer-course
```

---

# Environment Setup

Choose ONE option.

Option A → venv (recommended)  
Option B → Conda

---

# Option A — Python venv

Recommended for most students.

---

## macOS

Check Python:

```
python3 --version
```

Create environment:

```
python3 -m venv .venv
```

Activate:

```
source .venv/bin/activate
```

Upgrade pip:

```
python -m pip install --upgrade pip setuptools wheel
```

Install packages:

```
pip install -r env/requirements.txt
```

Launch Jupyter:

```
jupyter lab
```

Deactivate:

```
deactivate
```

---

## Linux

Check Python:

```
python3 --version
```

Create environment:

```
python3 -m venv .venv
```

Activate:

```
source .venv/bin/activate
```

Upgrade pip:

```
python -m pip install --upgrade pip setuptools wheel
```

Install packages:

```
pip install -r env/requirements.txt
```

Launch Jupyter:

```
jupyter lab
```

Deactivate:

```
deactivate
```

---

## Windows (PowerShell)

Check Python:

```
python --version
```

Create environment:

```
py -m venv .venv
```

Activate:

```
.venv\Scripts\Activate.ps1
```

If blocked:

```
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

Upgrade pip:

```
python -m pip install --upgrade pip setuptools wheel
```

Install packages:

```
pip install -r env/requirements.txt
```

Launch Jupyter:

```
jupyter lab
```

Deactivate:

```
deactivate
```

---

## Windows (Command Prompt)

```
py -m venv .venv
```

Activate:

```
.venv\Scripts\activate.bat
```

Upgrade pip:

```
python -m pip install --upgrade pip setuptools wheel
```

Install:

```
pip install -r env/requirements.txt
```

Launch:

```
jupyter lab
```

Deactivate:

```
deactivate
```

---

# Option B — Conda

Use if you already use Conda.

---

## macOS / Linux

Check Conda:

```
conda --version
```

Create environment:

```
conda env create -f env/environment.yml
```

Activate:

```
conda activate cw-course
```

Launch:

```
jupyter lab
```

Deactivate:

```
conda deactivate
```

---

## Windows (Anaconda Prompt / PowerShell)

Create:

```
conda env create -f env/environment.yml
```

Activate:

```
conda activate cw-course
```

Launch:

```
jupyter lab
```

Deactivate:

```
conda deactivate
```

---

# Running the Labs

After Jupyter opens, choose the correct folder.

CW Nano:

```
notebooks/cwnano/
```

CW Lite + CW305:

```
notebooks/cwlite_cw305/
```

Start with the setup check notebook.

---

# Updating Environment

### venv

```
pip install -r env/requirements.txt
```

### Conda

```
conda env update -f env/environment.yml --prune
```

---

# Verify Installation

```
python -c "import chipwhisperer as cw; print(cw.__version__)"
```

```
jupyter lab --version
```

---

# Troubleshooting

### Python not found

```
python --version
```

or

```
python3 --version
```

---

### Conda not found

Install Miniconda or Anaconda.

Restart terminal.

---

### Jupyter cannot import chipwhisperer

Close Jupyter.

Activate environment again.

Launch Jupyter from the same terminal.

---

### PowerShell activation blocked

```
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

---

# Notes

- Use only one environment option
- Do not edit the upstream folder
- Use the correct notebook folder for your hardware

---

# Updating Upstream Notebooks (Instructor)

```
git fetch newae-jupyter
git subtree pull --prefix=upstream/chipwhisperer-jupyter newae-jupyter main --squash
git push
```

Do not edit files inside `upstream/`.