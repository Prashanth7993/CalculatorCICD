# Continuous Integration (CI) for CalculatorCICD

## 🚀 Overview
This project implements a **Continuous Integration (CI) pipeline** in Python to ensure that code changes are properly formatted and tested before deployment. The CI pipeline performs the following tasks:

1. **Check Code Quality** – Uses `flake8` to check for PEP 8 violations and formatting issues.
2. **Run Unit Tests** – Uses `pytest` to execute test cases and verify the correctness of the code.
3. **Automate CI Process** – The `ci.py` script runs both checks automatically.

---

## 📌 Prerequisites
Make sure you have the following installed:
- **Python 3.x** (Ensure it is added to your system PATH)
- `flake8` (for code quality checks)
- `pytest` (for running test cases)
- `autopep8` (for auto-formatting, optional)

### Install Dependencies
Run the following command to install the required dependencies:
```bash
pip install flake8 pytest autopep8
```

---

## 🔹 Running the CI Pipeline

### 1️⃣ **Check Code Formatting & Indentation**
To check code formatting using `flake8`, run:
```bash
flake8 --max-line-length=100 .
```
✅ If no output is displayed, the code follows PEP 8 formatting.
❌ If there are errors, fix them manually or use auto-formatting:
```bash
autopep8 --in-place --aggressive --aggressive --max-line-length=100 *.py
```

---

### 2️⃣ **Run Unit Tests**
To execute test cases, use `pytest`:
```bash
pytest --maxfail=1 --disable-warnings -q
```
✅ If all tests pass, you’ll see output like:
```
. 3 passed in 0.45s
```
❌ If a test fails, it will show an error message indicating the issue.

To run tests for a specific file:
```bash
pytest tests/test_calculator.py
```
To run a specific test case:
```bash
pytest -k "test_addition"
```

---

### 3️⃣ **Run Complete CI Pipeline**
Instead of running checks separately, use the `ci.py` script:
```bash
python ci.py
```
This will:
- Check formatting (`flake8`)
- Run test cases (`pytest`)

If an error occurs, it will be displayed in the terminal.

---

## 🛠 CI Automation
To automate CI checks in a development workflow:
1. Integrate with **GitHub Actions** or **Jenkins**.
2. Run `ci.py` as a pre-commit hook to ensure code quality before pushing.
3. Add `flake8` and `pytest` in CI/CD pipelines for continuous testing.

---

## ✅ Summary
| **Step**  | **Command**  | **Purpose** |
|-----------|-------------|-------------|
| 🔹 **Check Formatting** | `flake8 --max-line-length=100 .` | Find indentation & PEP8 issues |
| 🔹 **Auto-Fix Formatting** | `autopep8 --in-place --aggressive --max-line-length=100 *.py` | Auto-fix formatting issues |
| 🔹 **Run All Tests** | `pytest --maxfail=1 --disable-warnings -q` | Execute unit tests |
| 🔹 **Run Specific Test** | `pytest -k "test_addition"` | Run a single test case |
| 🔹 **Run CI Checks** | `python ci.py` | Automate formatting & testing |

---

## 🚀 Next Steps
1. Run `python ci.py` and check for any issues.
2. If errors occur, review and fix them using `flake8` or `pytest`.
3. Integrate the script into your CI/CD pipeline for automated testing.

For any issues, feel free to contribute or open a discussion! 🎯

