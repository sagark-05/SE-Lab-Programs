# Lab 5: Static Code Analysis — Restaurant Order System

| Issue | Type | Line(s) | Description | Fix Approach |
|---|---|---|---|---|
| Mutable default argument | Bug | 15 | Default argument `[]` may be shared across function calls. | Change default to `None` and initialize a new list inside the function. |
| Use of `eval()` | Security | 42 | `eval(promo_expr)` can execute unintended code if the expression is untrusted. | Replace with a safe discount calculation or validated expression parser. |
| Weak MD5 hash | Security | 47 | MD5 is unsuitable for security-sensitive hashing due to collision weaknesses. | Use SHA-256 if a cryptographic hash is required. |
| Insecure random PIN | Security | 51 | `random.randint()` is not suitable for security-sensitive PIN generation. | Use the `secrets` module to generate the PIN. |
| Shell command execution | Security | 58 | `os.system()` with a filename may expose the program to command injection. | Avoid shell execution; use safe output or subprocess without `shell=True`. |
| Bare exception handler | Bug | 26 | Bare `except` silently catches all exceptions, and `pass` hides failures. | Catch the appropriate exception type and handle it explicitly. |
| Unused import | Code Quality | 6 | The imported `math` module is never used. | Remove the unused import. |
| Long lines | Code Quality | 18, 19, 75 | Lines exceed the recommended maximum length. | Split long statements into readable lines. |
| Missing final newline | Code Quality | 83 | The file does not end with a newline character. | Add a newline at the end of the file. |
| Missing function docstrings | Code Quality | 15, 23, 30, 40, 46, 50, 54, 61 | Functions do not have explanatory docstrings. | Add concise docstrings describing each function's purpose. |
| Non-standard function names | Code Quality | 15, 23, 30, 40 | Function names use camelCase instead of snake_case. | Rename functions using snake_case and update their call sites. |
| Unused variables | Code Quality | 31, 41, 63 | Variables `service_tax`, `base_bill`, and `t` are assigned but never used. | Remove unnecessary variables or use them correctly. |
| Comparison with None | Code Quality | 32 | The code uses `== None` instead of an identity comparison. | Replace `== None` with `is None`. |
| Unnecessary conditional | Code Quality | 34 | An `if`/`else` structure can be simplified because one branch already returns. | Simplify the conditional while preserving its behavior. |
| Unspecified file encoding | Code Quality | 55 | `open()` is used without specifying an encoding. | Specify `encoding="utf-8"` when opening the file. |
| File resource handling | Code Quality | 55 | The file is not managed using a context manager. | Use `with open(...)` to ensure the file is closed automatically. |
| String formatting | Code Quality | 19 | A regular string-formatting expression could use an f-string. | Replace it with an f-string where appropriate. |
| Redefined parameter name | Code Quality | 61 | The parameter `orders` shadows a name from the outer scope. | Rename the parameter if appropriate to improve clarity. |

