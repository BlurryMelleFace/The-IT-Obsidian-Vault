---
tags:
  - python
  - language
  - cheatsheet
  - devops
---
# Python

> [!INFO]
> **Python** is a high-level, interpreted language known for its readability and vast ecosystem. It is widely used in DevOps, Data Science, and Web Development.

**Related Notes:**
- [[Virtual Environment]] – Creating isolated environments (venv).
- [[Poetry]] – Modern dependency management.
- [[Black]] – Code formatter.
- [[Isort]] – Import sorter.

---

## 🏗️ Data Structures

### Lists (Mutable Sequence)
```python
my_list = [1, 2, 3]
my_list.append(4)
my_list.pop()      # Removes last element
item = my_list[0]  # Access first element
sliced = my_list[1:] # Slicing
```

### Dictionaries (Key-Value)
```python
my_dict = {"name": "Alice", "age": 30}
my_dict["city"] = "NY"
value = my_dict.get("country", "Unknown") # Safe access
keys = my_dict.keys()
values = my_dict.values()
```

### Sets (Unique Elements)
```python
my_set = {1, 2, 3, 3} # Becomes {1, 2, 3}
my_set.add(4)
is_in = 1 in my_set
```

### Tuples (Immutable)
```python
my_tuple = (1, 2)
# my_tuple[0] = 3 # Error!
x, y = my_tuple   # Unpacking
```

## 🛠️ Common Operations
### List Comprehensions
```python
squares = [x**2 for x in range(10) if x % 2 == 0]
```

### File I/O
```python
with open("file.txt", "r") as f:
    content = f.read()

with open("out.txt", "w") as f:
    f.write("Hello")
```

### Type Hinting
```python
def greet(name: str) -> str:
    return f"Hello, {name}"
```

## 📦 Virtual Environments & PIP
> *See [[Virtual Environment]] for details.*

```shell
# Create venv
python -m venv .venv

# Activate (Windows)
.venv\Scripts\activate

# Install requirements
pip install -r requirements.txt
```

## 🧪 Testing (pytest)
```shell
pip install pytest
pytest
```
```python
# test_sample.py
def test_answer():
    assert sum([1, 2]) == 3
```
