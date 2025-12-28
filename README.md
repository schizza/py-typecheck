# py-typecheck

Tiny runtime checker for typing annotations with an Option-like API.

## Install

```bash
pip install py-typecheck
```
### Usage
```python
from py_typecheck import checked

value: object = {"a": 1}

if (d := checked(value, dict[str, int])) is not None:
    print(d["a"] + 1)
```

### Notes
- bool is treated as not matching int (so True wont pass as int)
- always compare against `None` when using `checked` (don't rely on truthiness)
