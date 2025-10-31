# 🐍 0x00. Python - Variable Annotations

## 📘 Project Overview
This project introduces **Python variable annotations**, a feature added in **Python 3** that allows developers to specify expected data types for variables, function parameters, and return values.  
These annotations improve **readability, debugging, and static type checking** using tools like **mypy**.

---

## 🧠 Concepts Covered
You will learn:
- ✅ Type annotations in Python 3  
- ✅ How to use type annotations to specify function signatures and variable types  
- ✅ Duck typing  
- ✅ Validating code with **mypy**

---

## 🛠️ Requirements
- **Editors:** `vi`, `vim`, or `emacs`  
- **Python version:** 3.7 on Ubuntu 18.04 LTS  
- Files must:
  - End with a new line  
  - Start with `#!/usr/bin/env python3`  
  - Be executable  
  - Follow `pycodestyle` (version 2.5)  
- Each module, class, and function must contain **proper documentation** explaining its purpose.  
- All code must pass **mypy** type checking.

---

##  Resources
Before starting, read or watch:
- [Python 3 typing documentation](https://docs.python.org/3/library/typing.html)
- [MyPy cheat sheet](https://mypy.readthedocs.io/en/stable/cheat_sheet_py3.html)

---

##  Repository Structure
**GitHub repository:** `alx-backend-python`  
**Directory:** `0x00-python_variable_annotations`

---

##  Tasks Overview

### 0️⃣ 0. Basic annotations - add
**File:** `0-add.py`
```python
def add(a: float, b: float) -> float:
    """Return the sum of two floats."""
    return a + b




Example:

{'a': <class 'float'>, 'b': <class 'float'>, 'return': <class 'float'>}

1️⃣ 1. Basic annotations - concat

File: 1-concat.py

def concat(str1: str, str2: str) -> str:
    """Return concatenation of two strings."""
    return str1 + str2

2️⃣ 2. Basic annotations - floor

File: 2-floor.py

import math

def floor(n: float) -> int:
    """Return the floor of a float."""
    return math.floor(n)

3️⃣ 3. Basic annotations - to string

File: 3-to_str.py

def to_str(n: float) -> str:
    """Return the string representation of a float."""
    return str(n)

4️⃣ 4. Define variables

File: 4-define_variables.py

a: int = 1
pi: float = 3.14
i_understand_annotations: bool = True
school: str = "Holberton"

5️⃣ 5. Complex types - list of floats

File: 5-sum_list.py

from typing import List

def sum_list(input_list: List[float]) -> float:
    """Return the sum of a list of floats."""
    return sum(input_list)

6️⃣ 6. Complex types - mixed list

File: 6-sum_mixed_list.py

from typing import List, Union

def sum_mixed_list(mxd_lst: List[Union[int, float]]) -> float:
    """Return the sum of a list of ints and floats as a float."""
    return float(sum(mxd_lst))

7️⃣ 7. Complex types - string and int/float to tuple

File: 7-to_kv.py

from typing import Union, Tuple

def to_kv(k: str, v: Union[int, float]) -> Tuple[str, float]:
    """Return a tuple with a string and the square of a number."""
    return (k, float(v ** 2))

8️⃣ 8. Complex types - functions

File: 8-make_multiplier.py

from typing import Callable

def make_multiplier(multiplier: float) -> Callable[[float], float]:
    """Return a function that multiplies a float by a multiplier."""
    return lambda x: x * multiplier

9️⃣ 9. Let's duck type an iterable object

File: 9-element_length.py

from typing import Iterable, Sequence, List, Tuple

def element_length(lst: Iterable[Sequence]) -> List[Tuple[Sequence, int]]:
    """Return a list of tuples with each element and its length."""
    return [(i, len(i)) for i in lst]

🔟 10. Duck typing - first element of a sequence

File: 100-safe_first_element.py

from typing import Sequence, Any, Union

def safe_first_element(lst: Sequence[Any]) -> Union[Any, None]:
    """Return the first element of a sequence or None if empty."""
    if lst:
        return lst[0]
    return None

1️⃣1️⃣ 11. More involved type annotations

File: 101-safely_get_value.py

from typing import Mapping, Any, TypeVar, Union

T = TypeVar('T')

def safely_get_value(dct: Mapping, key: Any, default: Union[T, None] = None) -> Union[Any, T]:
    """Return value from dict safely, or a default if key not found."""
    if key in dct:
        return dct[key]
    return default

1️⃣2️⃣ 12. Type Checking with mypy

File: 102-type_checking.py

from typing import Tuple, List

def zoom_array(lst: Tuple, factor: int = 2) -> List:
    """Return a list where each item in the tuple is repeated `factor` times."""
    zoomed_in: List = [item for item in lst for i in range(factor)]
    return zoomed_in


Run mypy:

mypy 102-type_checking.py

🧩 Key Concepts Recap
Concept	Description	Example
Type Annotation	Specify data types for clarity and static checking	def add(a: float, b: float) -> float:
Duck Typing	Focus on behavior, not data type	Works if object supports needed methods
Union	Accept multiple types	Union[int, float]
Callable	Function as a return type	Callable[[float], float]
TypeVar	Generic type variable	T = TypeVar('T')
Mypy	Static type checker	mypy file.py
✅ Example Mypy Check
$ mypy 0-add.py
Success: no issues found in 1 source file

✍️ Author

By Lucky Baraka
📧 LinkedIn

💻 GitHub
