# Understanding Variables in Python
In programming, a variable is a fundamental concept. It acts as a named storage location in the computer's memory that holds a value. Think of it as a labeled container where you can store and retrieve data.

## What Are Variables? 📦
The "container" analogy is useful. Just as you might use a box to store items like books or toys, you use a variable to store data values like numbers, text, or more complex data structures.

<img width="455" height="195" alt="books and message" src="https://github.com/user-attachments/assets/f4946893-04bf-4f33-bb68-883630b8efa0" />


<img width="409" height="187" alt="hello message" src="https://github.com/user-attachments/assets/4b738d33-7144-454c-8a75-884feeb7caeb" />



A key feature of variables is that their contents can change. You can place a value in the container, and later, you can replace it with a new one. This "variability" is what gives them their name.

Anatomy of a Variable
A variable consists of two core components: a name (or identifier) and a value.

| Component | Description | Example (`age = 30`) |
| :--- | :--- | :--- |
| **Variable Name** | A unique label used to access the stored data. It's how you refer to the container. | `age` |
| **Variable Value** | The actual data stored inside the variable. This is the content of the container. | `30` |

* Note: In Python, the variable name points to a location in memory where the value is stored.


## Creating and Assigning Variables
You create a variable in Python using an assignment statement. The assignment operator (=) is used to assign a value to a variable name. In Python, you cannot declare a variable without also assigning it an initial value.

The syntax is straightforward: variable_name = value.

#### Assigning a string value to a variable named 'message'
message = "Hello, Python developers!"

#### Assigning an integer value to a variable named 'year'
year = 2025

#### The value of a variable can be updated
year = 2026 # The value of 'year' is now 2026

---

## Displaying Variable Output
* Simply assigning a value to a variable does not produce any visible output. 
* An assignment statement executes silently, storing the value in memory.
* To see the value stored in a variable, you need to explicitly instruct the program to display it. In Python, this is done using the built-in print() function.

#### Example: Without and With print()
Let's compare the two scenarios.

| Code | Output | Explanation |
| :--- | :--- | :--- |
| **Without `print()`** <br><br> ```python <br> topic = "Learning Python" <br> ``` | *No output is generated.* | The value `"Learning Python"` is stored in the `topic` variable, but nothing is displayed on the screen. |


| Code | Output | Explanation |
| :--- | :--- | :--- |
| **With `print()`** <br><br> ```python <br> topic = "Learning Python" <br> print(topic) <br> ``` | `Learning Python` | The `print()` function retrieves the value stored in the `topic` variable and displays it in the console. |

---

# Define a variable using other variables

## 📝 Understanding the Assignment Statement

When you see a line of code with a `=` in it, this is what we call an **assignment statement**. This statement plays a crucial role in programming and is fundamental to understand.

---

### The Two-Step Process 🧠

While it may look like a single action, assigning a variable is always a **two-step process**:

1.  ➡️ **Evaluate the Right Side**: First, the entire expression on the *right side* of the `=` is calculated and evaluated until it results in a single, final value.

2.  ⬅️ **Assign to the Left Side**: Then, and only then, that final value is stored in the variable on the *left side*.

<img width="766" height="202" alt="Screenshot 2025-08-31 133920" src="https://github.com/user-attachments/assets/fa05f794-59ac-4cf7-9881-eda43c2de4b3" />
---

#### 💡 Example in Action

Let's look at a simple line of code to see this process clearly:

```python
# A simple assignment statement
total_cost = 5 + (10 * 2)
```
## 🔗 Define a Variable Using Another Variable

* The value stored in a variable can also be defined using **other variables**. 
* This is a powerful feature that allows you to make your code more flexible and readable.

---

#### How It Works ⚙️

When you use one variable to define another, Python follows the same two-step assignment process:
1.  **Evaluate the Right Side**: Python first gets the current value of the variable on the right side of the `=`.
2.  **Assign to the Left Side**: It then assigns that value to the new variable on the left side.

---

##### 💡 Example in Action

For example, this code uses the `greeting` variable to set the value of `welcome_message`:

```python
# 1. Define the first variable
greeting = "Hello, developers!"

# 2. Use the first variable to define a second one
welcome_message = greeting

# 3. Print the new variable to see its value
print(welcome_message)
```

```python
first_name = "John"
last_name = "Lennon"

full_name = first_name + " " + last_name

print(full_name)
```

> ### 📌 A Quick Note on Spaces
>
> The `" "` (a single space inside quotes) is crucial when joining strings like names. It adds a space character to create a properly formatted and readable output.
>
> Without it, the strings are joined directly together.
>
> ---
>
> **For example:**
>
> 👎 **Without the space:**
>
> ```python
> first_name = "John"
> last_name = "Lennon"
> full_name = first_name + last_name
> print(full_name)
> # Output: JohnLennon
> ```
>
> 👍 **With the space:**
>
> ```python
> first_name = "John"
> last_name = "Lennon"
> full_name = first_name + " " + last_name
> print(full_name)
> # Output: John Lennon
> ```

---
## 🔄 Updating a Variable Using Its Own Value

So far, we've seen variables assigned with a simple value and variables assigned using expressions that include other variables. The new value of a variable can also be derived from its **current value**.

This process is fundamental for tasks like incrementing counters or building up strings.

### Example: Modifying a String

In the following example, the variable `message` is first assigned a string value. Then, it is reassigned a new value, which is the old value with three exclamation marks added to the end. 💡

```python
# The variable 'message' is first assigned a string value
message = "This is an important message"

# Then, its value is updated based on its previous value
message = message + "!!!"

print(message)
# Expected Output: This is an important message!!!
```

#### How It Works: This follows the two-step assignment rule.

* **Evaluate the Right Side:** Python first evaluates message + "!!!". It takes the current value ("This is an important message") and adds "!!!", resulting in a new string.

* **Assign to the Left Side:** This new, combined string is then assigned back to the message variable, overwriting the old value.
# 🏷️ Choosing a Good Name for a Variable

Good variable names are **vital** as they make your code easier to read and understand. Let’s discuss the rules and conventions you should follow when naming your variables.

---

### ✅ Valid Names

A variable name must follow specific rules to be valid in Python.

* It should begin with a **letter** (a-z, A-Z) or an **underscore** (`_`).
* It can only contain **letters**, **numbers** (0-9), and **underscores**. No other characters like `!` or `-` are allowed.
* Variable names are **case-sensitive** (`age`, `Age`, and `AGE` are three different variables).

| Valid Examples     | Invalid Examples | Reason Invalid              |
| :----------------- | :--------------- | :-------------------------- |
| `user_name`        | `1st_place`      | Cannot start with a number. |
| `_internal_data`   | `user-name`      | Cannot contain hyphens.     |
| `report2025`       | `user name`      | Cannot contain spaces.      |

---

### 🐍 Python Conventions (snake_case)

While not a strict rule, the official Python style guide (PEP 8) recommends a specific convention for variable names to ensure consistency across all Python code.

* In Python, it's common to use **lowercase letters** and separate words with **underscores**. This practice is known as **snake_case**.

```python
# Recommended (snake_case) ✅
user_first_name = "John"
````
#### Not recommended for Python (this is camelCase) ❌
#### userFirstName = "John"

### 📖 Descriptive Names

It is best to choose variable names according to what they are used for. A descriptive name makes the purpose of the variable immediately clear without needing extra comments.

* ✅ **Good:** Choose a name that describes the data it holds.
* ❌ **Bad:** Avoid single-letter names (unless they are for simple counters in short loops) or generic names that don't provide context.

```python
# Good, descriptive names ✅
word_to_find = "titanic"
user_age = 30
remaining_attempts = 3

# Bad, non-descriptive names ❌
w = "titanic"
a = 30
x = 3
```
# ❓ Do Variables Have a Type in Python?

The value inside a variable can be of any data type—such as an `int`, `str`, `float`, and so on. In Python, it’s not the variable (the "box") that has a type, but the **value** stored inside it.

This means a variable can hold a string at one moment and an integer the next. This is a core feature of Python's **dynamic typing**.

We can check the type of a value currently held by a variable using the `type()` function.

```python
# Initial assignments
message = "Hello world!"
pi = 3.14159

print(type(message))
# Expected Output: <class 'str'>

print(type(pi))
# Expected Output: <class 'float'>

# The type can be changed by reassigning the variable
print("---")
message = 10
print(type(message))
# Expected Output: <class 'int'>

```

## ⚠️ Why Consistency Matters

Although variables *can* change type, it is **not good practice**. As a programmer, knowing the type of each variable you use is crucial because different types behave differently with the same operators.

---

### ➕ The `+` Operator: Addition vs. Concatenation

Let's look at two variables that appear the same when printed but have different types.

```python
number1 = 100  # This is an integer
number2 = "100" # This is a string

print(number1) # Output: 100
print(number2) # Output: 100
```
* They look identical when printed, but watch what happens when we use the + operator on them:
```python
  # For integers, `+` means mathematical addition
print(number1 + number1)
# Expected Output: 200

# For strings, `+` means concatenation (joining them together)
print(number2 + number2)
# Expected Output: 100100
 ```
* This demonstrates that the variable's type completely changes the outcome of the operation.

** Type Errors: ** When Operators Fail
Not all operators are available for all types. While numbers can be divided using the / operator, attempting to divide a string by a number will cause a TypeError.

```python
number = "100"
print(number / 2)
# This code will crash with a TypeError because the '/'
# operator is not supported for a string and an integer.
```
---

### 🎓 Did You Know? Dynamic vs. Static Typing

 Python is a **dynamically typed** language. This means that a variable's type is checked *during* program execution (at runtime), and its type can change as you reassign it to different values. This behavior is not universal across all programming languages.

 ```python
 # In Python, the variable's type can change.
 my_variable = 10         # my_variable holds an integer
 print(type(my_variable)) # Output: <class 'int'>

 my_variable = "Hello!"   # Now the same variable holds a string
 print(type(my_variable)) # Output: <class 'str'>
 ```

 ---

 Many other languages, such as **Java** or **C++**, are **statically typed**. In these languages, a variable's type must be explicitly declared when it's created, and it **cannot** be changed later. The type checking is done *before* the program is run (at compile-time).

 ```java
 // In a statically typed language like Java, the type is fixed.
 int myVariable = 10;      // This variable can ONLY ever hold an integer.
 // myVariable = "Hello!"; // This line would cause a COMPILE ERROR.
 ```

 ---

 #### Key Differences

 | Feature | Dynamic Typing (Python) | Static Typing (Java, C++) |
 | :--- | :--- | :--- |
 | **Type Checking** | At Runtime | At Compile-Time |
 | **Flexibility** | High (variable types can change) | Low (types are fixed) |
 | **Error Detection** | Errors may appear late (during execution) | Catches type errors early (before running) |
 | **Code Verbosity** | Less verbose (no type declarations) | More verbose (requires type declarations) |

 Dynamic typing can be very convenient, but it also places more responsibility on you, the programmer. Misunderstanding a variable's type can lead to unexpected behavior and bugs that are hard to track down.

---

## Printing with F-Strings in Python

So far, we have often used the `print()` function to display a single variable or expression. But what if we want to combine text and variables in a single, readable `print()` statement?

### Introducing: Formatted String Literals (`f-strings`)

**F-strings** provide a modern, concise, and highly readable way to embed Python expressions directly inside string literals.

The syntax might seem a bit unusual at first, but `f-strings` are often the simplest and most powerful method for string formatting in Python.

Take a look at this example:

```python
# Declare a variable for speed
speed = 50
unit = "mph"

# Use an f-string to print a formatted message
# The variables are placed inside curly braces {}
print(f"The current speed is {speed} {unit}.")
```

 ##### How It Works:

* Prefix f: The string must be prefixed with the letter f or F. This tells Python it's a formatted string literal.

* Expressions in Braces {}: Any valid Python expression can be placed inside curly braces {}. Python evaluates these expressions at runtime.

* Result: The evaluated result of the expression is converted to a string and inserted at that position in the final output.

* ## Breaking Down the F-String Syntax

Let's look at the components of an `f-string` more closely.

* **The `f` Prefix:** The string literal must begin with the character `f` or `F`. This crucial prefix signals to Python that the following string is an f-string and should be processed for embedded expressions.

* **Curly Braces `{}`:** Inside the string, you place variable names (like `{speed}`) or even entire expressions (like `{speed * 2}`) within curly braces. Python replaces these placeholders with the actual value of the variable or the result of the expression at runtime.

### Using Multiple Variables in a Single F-String

A single `f-string` can seamlessly contain as many variables as you need, making it easy to construct complex sentences.

For example, here we combine three different variables into one cohesive output:

```python
name = "Anna"
age = 37
city = "Madrid"

print(f"Hi {name}, you are {age} years old. You live in {city}.")
Hi Anna, you are 37 years old. You live in Madrid.
```

## Using Expressions Inside F-Strings

The power of an `f-string` goes beyond simply inserting variables. You can place any valid Python **expression** inside the curly braces, and it will be evaluated when the string is created.

> **Key Idea:** This means you can perform calculations, call functions, and access object attributes directly within the string itself.

Here is the example you provided, which calculates the age for the next year directly within the `print()` statement:

```python
name = "Anna"
age = 37

print(f"Hi {name}, you are {age} years old.")

# The expression 'age + 1' is calculated before being inserted into the string.
print(f"You're gonna be {age + 1} next year!")
Hi Anna, you are 37 years old.
You're gonna be 38 next year!
```
---

## 🇹🇷 Python'da F-String ile Metin Biçimlendirme (Teknik Açıklama)

**F-String** (Formatted String Literals - Biçimlendirilmiş Dizi Literalleri), Python 3.6 ile tanıtılan modern, güçlü ve okuması kolay bir metin biçimlendirme yöntemidir. Amacı, metinler içerisine değişkenleri veya ifadeleri yerleştirmeyi eski yöntemlere (`%` operatörü veya `str.format()` metodu) göre çok daha basit ve performanslı bir hale getirmektir.

### Temel Söz Dizimi (Syntax)

Bir F-String oluşturmak için, metnin başına `f` veya `F` öneki getirilir. Metin içerisine yerleştirilmek istenen değişken veya Python ifadesi ise `{}` (süslü parantez) içine yazılır.

> **Genel Yapı:**
> `f"Metin... {ifade} ... daha fazla metin."`

### Temel Özellikler ve Örnekler

#### 1. Değişkenlerin Kullanımı
En temel kullanım, bir metin içerisine doğrudan değişken değerlerini eklemektir.

```python
isim = "Ayşe"
yas = 30

print(f"Kullanıcının adı {isim} ve {yas} yaşındadır.")
Kullanıcının adı Ayşe ve 30 yaşındadır.
```

#### 2. İfadelerin Değerlendirilmesi
F-String'lerin gücü, süslü parantezler içine sadece değişken değil, herhangi bir geçerli Python ifadesi yazılabilmesinden gelir. Bu ifadeler çalışma zamanında (runtime) değerlendirilir.

```python
adet = 10
birim_fiyat = 25

print(f"{adet} adet ürünün toplam tutarı: {adet * birim_fiyat} TL.")
print(f"Seneye {yas + 1} yaşında olacak!")
10 adet ürünün toplam tutarı: 250 TL.
Seneye 31 yaşında olacak!
```

#### 3. Fonksiyon ve Metot Çağrıları
Değişkenler üzerinde metotlar veya genel fonksiyonlar çağırabilirsiniz.

```python
mesaj = "merhaba dünya"

print(f"Mesajın orijinal hali: '{mesaj}'")
print(f"Büyük harflerle: '{mesaj.upper()}'")
print(f"Mesajın uzunluğu: {len(mesaj)}")

Mesajın orijinal hali: 'merhaba dünya'
Büyük harflerle: 'MERHABA DÜNYA'
Mesajın uzunluğu: 13
```
### İleri Seviye Biçimlendirme Seçenekleri

Süslü parantez içinde, ifadeden sonra iki nokta üst üste (`:`) kullanarak özel biçimlendirme talimatları verebilirsiniz. Bu, özellikle sayılar, tarihler ve metin hizalamaları için çok kullanışlıdır.

#### Sayı Biçimlendirme (Ondalık ve Hizalama)

Örneğin, ondalık basamak sayısını sınırlayabilir veya metni belirli bir alana hizalayabilirsiniz.

```python
pi_sayisi = 3.14159265
sayi = 1250000

# Ondalık basamak sayısını sınırlama (.2f -> 2 basamak göster)
print(f"Pi sayısının yaklaşık değeri: {pi_sayisi:.2f}")

# Sayıyı binlik ayraçlarla yazdırma (,)
print(f"Büyük sayı: {sayi:,}")

# Metni belirli bir alana hizalama (>10 -> 10 karakterlik alana sağa yasla)
print(f"Sağa yaslı: {'merhaba':>20}")
i sayısının yaklaşık değeri: 3.14
Büyük sayı: 1,250,000
Sağa yaslı:              merhaba
```
### 🐍 Python F-String'lerinin Avantajları

F-String'ler, modern Python'da metin biçimlendirme için standart haline gelmiştir. Başlıca avantajları şunlardır:

* 🚀 **Performans:** Genellikle diğer metin biçimlendirme yöntemlerinden (`%` veya `.format()`) daha hızlıdır çünkü ifadeler doğrudan çalışma anında (runtime) yorumlanır.

* 👀 **Okunabilirlik:** Değişkenler ve ifadeler, kullanılacakları metnin tam içinde yer alır. Bu, kodu okumayı ve anlamayı çok daha kolay ve sezgisel hale getirir.

* 🔧 **Esneklik:** Süslü parantezler (`{}`) içerisine herhangi bir geçerli Python ifadesi (hesaplamalar, fonksiyon çağrıları vb.) yazılabilmesi, onu son derece güçlü ve esnek kılar.
---

### 📦 Python Değişkenleri: Saklama Kutusu Metaforu

Bilgisayarınızın hafızasını büyük bir depo odası gibi düşünün. Değişkenler, bu depoda verilerinizi (bilgilerinizi) saklamak ve düzenlemek için kullandığınız, üzerleri etiketlenmiş kutulardır.

| Kavram (Concept) | 📦 Saklama Kutusu Metaforu | 📝 Açıklama |
| :--- | :--- | :--- |
| **Değişken (Variable)** | **Etiketli Saklama Kutusu** | Verilerinizi içinde saklamak için kullandığınız, üzerinde bir isim yazan bir kutudur. |
| **Değişken Adı (Variable Name)** | **Kutunun Üzerindeki Etiket** | Kutunun içinde ne olduğunu bilmek ve onu diğer kutulardan ayırmak için kullandığınız addır. Örneğin: `puan`, `kullanici_adi`. |
| **Değer (Value)** | **Kutunun İçindeki Eşya** | Kutunun içinde sakladığınız asıl şeydir. Bu bir elma (🍎 `int`), bir mektup (📜 `str`) veya başka kutularla dolu bir sepet (🧺 `list`) olabilir. |
| **Atama İşlemi (`=`)** | **Eşyayı Kutuya Koymak** | Bir değeri (eşyayı) alıp, belirli bir etikete (isme) sahip kutunun içine yerleştirme eylemidir. `puan = 100` |
| **Değere Erişmek** | **Kutunun İçine Bakmak** | Etiketine bakarak doğru kutuyu bulup, içinde ne olduğunu kontrol etmektir. `print(puan)` |
| **Yeniden Atama** | **Kutunun İçindekini Değiştirmek**| Aynı etiketli kutuyu açıp, içindeki eski eşyayı çıkarıp yerine yeni bir eşya koymaktır. Kutunun etiketi (`adı`) aynı kalır ama içeriği (`değeri`) değişir. |

---

### 📦 Python Değişkenleri: Saklama Kutusu Metaforu ( Turkish)

Bilgisayarınızın hafızasını büyük bir depo odası gibi düşünün. Değişkenler, bu depoda verilerinizi (bilgilerinizi) saklamak ve düzenlemek için kullandığınız, üzerleri etiketlenmiş kutulardır.

| Kavram (Concept) | 📦 Saklama Kutusu Metaforu | 📝 Açıklama |
| :--- | :--- | :--- |
| **Değişken (Variable)** | **Etiketli Saklama Kutusu** | Verilerinizi içinde saklamak için kullandığınız, üzerinde bir isim yazan bir kutudur. |
| **Değişken Adı (Variable Name)** | **Kutunun Üzerindeki Etiket** | Kutunun içinde ne olduğunu bilmek ve onu diğer kutulardan ayırmak için kullandığınız addır. Örneğin: `puan`, `kullanici_adi`. |
| **Değer (Value)** | **Kutunun İçindeki Eşya** | Kutunun içinde sakladığınız asıl şeydir. Bu bir elma (🍎 `int`), bir mektup (📜 `str`) veya başka kutularla dolu bir sepet (🧺 `list`) olabilir. |
| **Atama İşlemi (`=`)** | **Eşyayı Kutuya Koymak** | Bir değeri (eşyayı) alıp, belirli bir etikete (isme) sahip kutunun içine yerleştirme eylemidir. `puan = 100` |
| **Değere Erişmek** | **Kutunun İçine Bakmak** | Etiketine bakarak doğru kutuyu bulup, içinde ne olduğunu kontrol etmektir. `print(puan)` |
| **Yeniden Atama** | **Kutunun İçindekini Değiştirmek**| Aynı etiketli kutuyu açıp, içindeki eski eşyayı çıkarıp yerine yeni bir eşya koymaktır. Kutunun etiketi (`adı`) aynı kalır ama içeriği (`değeri`) değişir. |

---

### Metaforun Kodla Gösterimi

```python
# 'puan' etiketli bir kutu oluştur ve içine 100 elması koy (Atama)
puan = 100

# 'kullanici_adi' etiketli bir kutu oluştur ve içine "Hande" mektubunu koy
kullanici_adi = "Hande"

# 'puan' etiketli kutunun içine bak ve içindekini söyle (Değere Erişmek)
print(f"{kullanici_adi} kullanıcısının puanı: {puan}")

# 'puan' etiketli kutuyu aç, içindeki 100 elmasını çıkar
# ve yerine 150 elması koy (Yeniden Atama)
puan = 150

# Kutunun içine tekrar bak
print(f"{kullanici_adi} kullanıcısının YENİ puanı: {puan}")

OutPut:
Hande kullanıcısının puanı: 100
Hande kullanıcısının YENİ puanı: 150
```
