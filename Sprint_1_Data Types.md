# Python Data Types: A Technical Overview

In Python, a data type is a classification that specifies which type of value a variable can hold and what type of mathematical, relational, or logical operations can be applied to it without causing an error. Python is a dynamically typed language, which means you don't need to explicitly declare the data type of a variable; the interpreter infers it at runtime.

This document provides a technical breakdown of Python's fundamental built-in data types.

## Table of Contents
1.  [Numeric Types](#numeric-types)
    - [`int`](#integers-int)
    - [`float`](#floating-point-numbers-float)
    - [`complex`](#complex-numbers-complex)
2.  [Sequence Types](#sequence-types)
    - [`list`](#lists-list)
    - [`tuple`](#tuples-tuple)
    - [`range`](#ranges-range)
3.  [Text Sequence Type](#text-sequence-type)
    - [`str`](#strings-str)
4.  [Mapping Type](#mapping-type)
    - [`dict`](#dictionaries-dict)
5.  [Set Types](#set-types)
    - [`set`](#sets-set)
    - [`frozenset`](#frozen-sets-frozenset)
6.  [Boolean Type](#boolean-type)
    - [`bool`](#booleans-bool)
7.  [None Type](#none-type)
    - [`NoneType`](#the-none-type-nonetype)
8.  [Summary Table](#summary-of-properties)


## Numeric Types
Numeric types represent numbers. They are created by number literals or as a result of arithmetic operations. All numeric types are **immutable**.

### Integers (`int`)
-   **Description:** Represents positive or negative whole numbers without a decimal point.
-   **Characteristics:**
    -   **Immutable:** Once created, their value cannot be changed.
    -   **Precision:** Python integers have arbitrary precision, meaning they can be as large as the memory of your machine allows.
-   **Creation:**
    ```python
    my_integer = 100
    negative_int = -42
    large_int = 98765432109876543210
    ```
-   **Common Operations:** Standard arithmetic (`+`, `-`, `*`, `/`, `//` for floor division, `%` for modulus, `**` for exponentiation).

### Floating-Point Numbers (`float`)
-   **Description:** Represents real numbers with a decimal point. They are implemented as double-precision floating-point numbers (64-bit).
-   **Characteristics:**
    -   **Immutable:** Their value cannot be changed.
    -   **Precision:** Subject to machine-level floating-point precision errors (e.g., `0.1 + 0.2` is not exactly `0.3`).
-   **Creation:**
    ```python
    my_float = 3.14159
    scientific_notation = 1.23e4  # Represents 1.23 * 10^4
    ```
-   **Common Operations:** Same as integers.

### Complex Numbers (`complex`)
-   **Description:** Represents numbers with a real and an imaginary part, denoted with a `j` or `J`.
-   **Characteristics:**
    -   **Immutable:** Their value cannot be changed.
-   **Creation:**
    ```python
    my_complex = 3 + 4j
    ```
-   **Common Operations:** Access real and imaginary parts via attributes (`my_complex.real`, `my_complex.imag`).

## Sequence Types
A sequence is an ordered collection of items, accessible by index.

### Lists (`list`)
-   **Description:** A versatile, ordered collection of items. Lists are one of the most used data structures in Python.
-   **Characteristics:**
    -   **Mutable:** Elements can be added, removed, or changed after creation.
    -   **Ordered:** Items maintain a stable order.
    -   **Heterogeneous:** Can contain items of different data types.
-   **Creation:**
    ```python
    my_list = [1, "hello", 3.14, True]
    empty_list = []
    ```
-   **Common Operations & Methods:**
    -   **Indexing & Slicing:** `my_list[0]`, `my_list[1:3]`
    -   **Modification:** `my_list[1] = "world"`
    -   **Methods:** `.append()`, `.extend()`, `.insert()`, `.pop()`, `.remove()`, `.sort()`
    -   **Length:** `len(my_list)`

### Tuples (`tuple`)
-   **Description:** An ordered, unchangeable collection of items. Often used for data that should not be modified.
-   **Characteristics:**
    -   **Immutable:** Once a tuple is created, you cannot change its elements.
    -   **Ordered:** Items maintain a stable order.
    -   **Performance:** Slightly more memory-efficient and faster to iterate over than lists.
-   **Creation:**
    ```python
    my_tuple = (1, "hello", 3.14)
    single_item_tuple = (42,) # The trailing comma is mandatory
    ```
-   **Common Operations:** Indexing, slicing, and `len()` work like lists. No methods for modification are available.

### Ranges (`range`)
-   **Description:** Represents an immutable sequence of numbers and is commonly used for looping a specific number of times in `for` loops.
-   **Characteristics:**
    -   **Immutable:** Cannot be changed after creation.
    -   **Memory Efficient:** Only stores the start, stop, and step values, generating numbers on the fly.
-   **Creation:**
    ```python
    # Represents numbers 0, 1, 2, 3, 4
    for i in range(5):
        print(i)
    
    # Represents numbers 2, 4, 6, 8
    for i in range(2, 10, 2):
        print(i)
    ```

## Text Sequence Type

### Strings (`str`)
-   **Description:** An ordered, immutable sequence of Unicode characters.
-   **Characteristics:**
    -   **Immutable:** You cannot change a character within a string. Operations that seem to modify a string actually create a new one.
    -   **Ordered:** Characters are in a defined sequence.
-   **Creation:**
    ```python
    my_string = "Hello, World!"
    another_string = 'Python is fun.'
    multiline_string = """This is a
    multi-line string."""
    ```
-   **Common Operations & Methods:**
    -   **Concatenation & Repetition:** `+`, `*`
    -   **Formatting:** f-strings are the modern standard: `f"My name is {name}"`
    -   **Methods:** `.upper()`, `.lower()`, `.strip()`, `.split()`, `.join()`, `.replace()`, `.startswith()`

## Mapping Type

### Dictionaries (`dict`)
-   **Description:** A mutable, unordered (in Python < 3.7) or ordered (in Python 3.7+) collection of unique key-value pairs.
-   **Characteristics:**
    -   **Mutable:** Key-value pairs can be added, modified, or removed.
    -   **Ordered:** As of CPython 3.7+, dictionaries preserve insertion order.
    -   **Keys:** Keys must be of an immutable (hashable) type (e.g., `str`, `int`, `tuple`).
-   **Creation:**
    ```python
    my_dict = {
        "name": "Alice",
        "age": 30,
        "is_student": False
    }
    empty_dict = {}
    ```
-   **Common Operations & Methods:**
    -   **Accessing:** `my_dict["name"]`
    -   **Adding/Updating:** `my_dict["age"] = 31`
    -   **Deleting:** `del my_dict["is_student"]`
    -   **Methods:** `.keys()`, `.values()`, `.items()`, `.get()`

## Set Types
Sets are unordered collections of unique items.

### Sets (`set`)
-   **Description:** A mutable, unordered collection of unique, hashable elements.
-   **Characteristics:**
    -   **Mutable:** Elements can be added or removed.
    -   **Unordered:** Items do not have a defined order.
    -   **Unique:** Automatically handles duplicate elements.
-   **Creation:**
    ```python
    my_set = {1, 2, 3, 4, 4, 5} # Becomes {1, 2, 3, 4, 5}
    empty_set = set() # Note: {} creates an empty dictionary
    ```
-   **Common Operations & Methods:**
    -   **Mathematical Set Operations:** Union (`|`), intersection (`&`), difference (`-`), symmetric difference (`^`).
    -   **Methods:** `.add()`, `.remove()`, `.discard()`, `.pop()`

### Frozen Sets (`frozenset`)
-   **Description:** An immutable version of a set.
-   **Characteristics:**
    -   **Immutable:** Its contents cannot be changed after creation.
    -   **Hashable:** Because it's immutable, a `frozenset` can be used as a dictionary key or as an element of another set.
-   **Creation:**
    ```python
    my_frozenset = frozenset([1, 2, 3, 4])
    ```

## Boolean Type

### Booleans (`bool`)
-   **Description:** Represents one of two values: `True` or `False`. It's a subclass of `int`, where `True` corresponds to `1` and `False` to `0`.
-   **Characteristics:**
    -   **Logical Values:** Used for conditional logic and control flow.
    -   **Truthiness:** Most Python objects have an inherent boolean value. Empty collections (`[]`, `()`, `{}`), empty strings (`""`), `0`, and `None` are considered `False`. All other objects are considered `True`.
-   **Creation:**
    ```python
    is_active = True
    has_permission = False
    ```

## The None Type

### NoneType (`None`)
-   **Description:** A special data type that has only one value: `None`.
-   **Characteristics:**
    -   **Singleton:** There is only one instance of `None` in a Python program.
    -   **Represents Absence:** It is used to signify the absence of a value or a null value. It is a common default return value for functions that don't explicitly return anything.
-   **Usage:**
    ```python
    result = None
    if result is None:
        print("No result yet.")
    ```

## Summary of Properties

| Data Type | Mutability  | Ordered      | Description                          | Example Syntax                   |
|-----------|-------------|--------------|--------------------------------------|----------------------------------|
| `int`     | Immutable   | N/A          | Whole numbers                        | `x = 100`                        |
| `float`   | Immutable   | N/A          | Decimal numbers                      | `y = 3.14`                       |
| `str`     | Immutable   | Yes          | Sequence of characters               | `s = "hello"`                    |
| `list`    | **Mutable** | Yes          | Ordered collection of items          | `l = [1, 'a', 2.0]`              |
| `tuple`   | Immutable   | Yes          | Ordered, unchangeable collection     | `t = (1, 'a', 2.0)`              |
| `dict`    | **Mutable** | Yes (3.7+)   | Key-value pairs                      | `d = {'key': 'value'}`           |
| `set`     | **Mutable** | No           | Unordered collection of unique items | `s = {1, 2, 3}`                  |
| `frozenset`| Immutable | No           | Unchangeable set                     | `fs = frozenset({1, 2, 3})`      |
| `bool`    | Immutable   | N/A          | Logical True/False values            | `b = True`                       |
| `NoneType`| Immutable   | N/A          | Represents the absence of a value    | `n = None`                       |

---

### 🐍 Python Veri Tipleri: Mutfak Kileri Metaforu (Turkish)

Programınızın hafızasını bir mutfak kileri gibi düşünün. Kullandığınız her veri tipi, bu kilerde sakladığınız farklı bir yiyecek türü veya saklama kabı gibidir.

| Veri Tipi (Data Type) | 🥫 Mutfak Kileri Metaforu | 📝 Açıklama |
| :--- | :--- | :--- |
| **`int` (Integer)** | 🍎 **Elmalar** | Tam, bütün, sayılabilen nesnelerdir. Yarım elma olmaz; her zaman tam sayıdır. (`5`, `-10`, `1500`) |
| **`float` (Float)** | 🥛 **Süt veya Su** | Kesin bir ölçüyle ölçülebilen, ondalıklı olabilen sıvılardır. `1.5` litre süt gibi. (`3.14`, `-0.5`, `99.0`) |
| **`str` (String)** | 🏷️ **Kavanoz Etiketi** | Kavanozun içindekini (veriyi) açıklayan metindir. "Tuz", "Şeker" gibi. Değiştirilemez; yeni bir etiket yazmanız gerekir. |
| **`bool` (Boolean)** | 💡 **Lamba Düğmesi** | Sadece iki durumu vardır: Açık (`True`) veya Kapalı (`False`). Arası yoktur. |
| **`list` (Liste)** | 🛒 **Alışveriş Listesi** | Üzerine maddeler ekleyip (`append`), silebilir (`remove`), sırasını değiştirebileceğiniz esnek bir listedir. Sıra önemlidir. |
| **`tuple` (Demet)** | 📜 **Basılı Yemek Tarifi** | Adımların sırası bellidir ve yazdırıldıktan sonra değiştirilemez. Güvenilir ve sabittir. |
| **`dict` (Sözlük)** | 🗄️ **Baharat Çekmecesi** | Her baharatın (değer) kendine ait bir etiketi (anahtar) vardır. "Kekik" etiketine bakarak kekiğe ulaşırsınız, sırasıyla aramazsınız. |
| **`set` (Küme)** | 🧺 **Meyve Sepeti** | İçine meyveleri atarsınız. Her meyveden sadece bir tane olur (benzersizdir) ve hangisinin nerede durduğunun (sırasının) bir önemi yoktur. |
| **`None` (`NoneType`)**| 텅 **Boş Kavanoz** | Henüz içine bir şey konulmamış, boşluğu temsil eden bir yer tutucudur. "Sıfır" veya "boş metin" değil, sadece "içinde değer yok" demektir. |
