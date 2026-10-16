# Lab 5: Static Code Analysis — Reflection

## 1. What types of issues did the static analysis tools identify?

Pylint identified code-quality problems such as missing docstrings, non-standard function names, unused variables, a mutable default argument, and unnecessary conditional logic. Flake8 identified style violations, including long lines, an unused import, a bare exception handler, and a missing final newline. Bandit identified security risks such as the use of `eval()`, weak MD5 hashing, insecure random number generation, silent exception handling, and shell command execution.

## 2. Which issue was the most serious, and why?

The use of `eval()` was one of the most serious issues because it could execute unintended code if an untrusted promotional expression were supplied. I replaced it with a numeric discount calculation that validates the discount rate. I also replaced MD5 with SHA-256 for ticket hashing, used the `secrets` module for PIN generation, and removed shell command execution to reduce security risks.

## 3. How did fixing the issues improve the program?

The fixes improved readability, maintainability, and security. I added function docstrings, changed function names to snake_case, removed unused variables and imports, corrected the mutable default argument, improved exception handling, and used a context manager with explicit UTF-8 encoding for file operations. I also preserved the main restaurant-order functionality, including order placement, cancellation, bill calculation, PIN generation, and kitchen-order export.

## 4. What were the final analysis results, and what did you learn?

Initially, Pylint rated the program 4.81/10, Bandit reported five security findings, and Flake8 reported multiple style and code-quality violations. After fixing the issues, Pylint rated the program 10.00/10, Bandit reported no issues, and Flake8 produced no violations. I learned that a program can run successfully while still containing security vulnerabilities and maintainability problems. Static analysis tools help identify these problems early, but the program must also be tested to ensure that the fixes preserve its intended behavior.
