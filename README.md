# Method signature checking decorator for Python 3

## Samples:

```python
from typecheck import *
```

```python
@typecheck
def foo(i: int, x = None, s: str = "default") -> bool:
    ...
```

```python
@typecheck
def foo(*args, k1: int, k2: str = "default", k3 = None) -> nothing:
    ...
```

```python
@typecheck
def foo(ostream: with_attr("write", "flush"), f: optional(callable) = None):
    ...
```

```python
divisible_by_three = lambda x: x % 3 == 0
@typecheck
def foo(i: by_regex("^[0-9]+$")) -> divisible_by_three:
    ...
```

```python
@typecheck
def reverse_2_tuple(t: (str, bytes)) -> (bytes, str):
    ...
```

```python
@typecheck
def reverse_3_list(t: [int, float, bool]) -> [bool, float, int]:
    ...
```

```python
@typecheck
def extract_from_dict(d: dict_of(int, str), k: tuple_of(int)) -> list_of(str):
    ...
```

```python
@typecheck
def contains(x: int, xs: set_of(int)) -> bool:
    ...
```

```python
@typecheck
def set_level(level: one_of(1, 2, 3)):
    ...
```

```python
@typecheck
def accept_number(x: either(int, by_regex("^[0-9]+$"))):
    ...

```

```python
@typecheck_with_exceptions(input_parameter_error = MemoryError)
def custom_input_error(x: int): # now custom_input_error("foo") throws MemoryError
    ...
```

```python
@typecheck_with_exceptions(return_value_error = TypeError)
def custom_return_error() -> str: # now custom_return_error() throws TypeError
    return 1
```
