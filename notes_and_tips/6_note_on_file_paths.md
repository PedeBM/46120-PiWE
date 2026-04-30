# Working with File Paths in Python

**Context:** Script `examples/main.py` needs to load `inputs/sample_time_series.csv`, in the repo here: https://github.com/ju-feng-dk/FinalProjectExample

The repo has the following folder structure:
```
FinalProjectExample/
├── .gitignore
├── LICENSE
├── README.md
├── pyproject.toml
├── inputs/                        # Input data folder
│   └── sample_time_series.csv
├── outputs/                       # Output folder
│   └── time_series_plot.png
├── examples/
│   └── main.py                    # The script we are working with
├── src/
│   └── my_toy_package/
│       ├── __init__.py
│       ├── classes_cls.py
│       └── functions_mod.py              
└── tests/
    ├── test_classes.py
    └── test_functions.py
```

---

## 1. Absolute Path (depends on specific machine)

```python
# Windows example
with open("C:/Users/name/FinalProjectExample/inputs/sample_time_series.csv", "r") as f:
    data = f.read()

# Linux/macOS example
with open("/home/name/FinalProjectExample/inputs/sample_time_series.csv", "r") as f:
    data = f.read()
```

| Pros | Cons |
|------|------|
| Works regardless of CWD (current working directory)| **Not portable** – hardcoded user/project path |
| Simple | Breaks on different machines or project locations |

---

## 2. Relative Path (depends on current working directory)

```python
# Assumes script is run from examples folder (FinalProjectExample/examples)
with open("../inputs/sample_time_series.csv", "r") as f:
    data = f.read()
```

| Pros | Cons |
|------|------|
| Portable across machines (if folder structure preserved) | **Brittle** – works only when CWD = FinalProjectExample/examples |
| Short and readable | Fails if script run from elsewhere or imported |

---

### 3. `os.path` (traditional, still used)

```python
import os

# Get script location
script_dir = os.path.dirname(os.path.abspath(__file__))   # FinalProjectExample/examples/

# Navigate up to project root (one level up from examples/)
project_root = os.path.dirname(script_dir)               # FinalProjectExample/

# Build path to data file
data_file = os.path.join(project_root, "inputs", "sample_time_series.csv")

# Read file
with open(data_file, "r") as f:
    data = f.read()
```

| Pros | Cons |
|------|------|
| Works regardless of CWD (uses `__file__`) | More verbose and nested function calls |
| Cross‑platform (handles separators via `os.path.join`) | String‑based, not as intuitive |
| No extra imports beyond `os` | Prone to errors with nested `dirname` calls |

---

### 4. `pathlib` (modern, recommended)

```python
from pathlib import Path

# Get script location
script_dir = Path(__file__).parent                     # FinalProjectExample/examples/

# Navigate up to project root (one level up)
project_root = script_dir.parent                       # FinalProjectExample/

# Build path to data file
data_file = project_root / "inputs" / "sample_time_series.csv"

# Read file
with open(data_file, "r") as f:
    data = f.read()
```

| Pros | Cons |
|------|------|
| Works regardless of CWD | Requires Python 3.4+ (now standard) |
| Cross‑platform automatically | |
| Intuitive `/` operator and rich methods (`.parent`, `.read_text()`, `.exists()`) | |

---

## ✅ Recommendation: `pathlib`

```python
from pathlib import Path

BASE = Path(__file__).parent.parent          # FinalProjectExample/
INPUT_FILE = BASE / "inputs" / "sample_time_series.csv"

with open(INPUT_FILE, "r") as f:
    data = f.read()
```

This is the **most readable, robust, and portable** way for modern scientific Python code. It works **no matter where you run the script from** (project root, script directory, or anywhere else), because the path is always built relative to the script's own location using `__file__`.
