## 🧮 Arithmetic Operators in Python

Now that you are familiar with fundamental concepts like `values`, `types`, and the `print()` function, we can explore core programming constructs. This section focuses on the arithmetic operators used to perform mathematical calculations in Python.

You have already encountered basic operators like `+` and `*`. The table below provides a comprehensive list of the most common arithmetic operators available in Python.

| Operator | Name | Example | Result |
| :---: | :--- | :--- | :--- |
| `+` | Addition | `2 + 4` | `6` |
| `-` | Subtraction | `10 - 2.5` | `7.5` |
| `*` | Multiplication | `-2 * 123` | `-246` |
| `/` | Division | `9 / 2` | `4.5` |
| `//`| Floor Division | `9 // 2` | `4` |
| `%` | Modulo (Remainder) | `9 % 2` | `1` |
| `**`| Exponentiation | `2 ** 3` | `8` |

> **Key Point:** The standard division operator (`/`) always returns a `float` (a number with a decimal point). To get an integer result by discarding the fractional part, you must use the floor division operator (`//`).

## ➗ Division in Python: Standard (`/`) vs. Floor (`//`)

Python provides two distinct division operators, each serving a different purpose. Understanding the difference is crucial for writing accurate and predictable code, especially when dealing with numerical data.

---

### Standard Division (`/`)

This is the default division operator. It performs floating-point division, and the result is **always a `float`** (a number with a decimal point), even if the numbers divide evenly.

For example, to convert 645 minutes into an exact number of hours, you would use standard division:

```python
minutes = 645
hours_as_float = minutes / 60

print(f"645 minutes is exactly {hours_as_float} hours.")
645 minutes is exactly 10.75 hours.
```

### Floor Division (`//`)

This operator performs **floor division**. It divides the first operand by the second and **rounds the result down** to the nearest whole number (the "floor"), returning it as an **integer**. This is useful when you only need to know how many full times a number fits into another, completely disregarding the remainder.

#### Example: Calculating Whole Hours

To find only the number of **whole hours** in 645 minutes, we use the floor division operator:

```python
minutes = 645
whole_hours = minutes // 60

print(f"There are {whole_hours} whole hours in {minutes} minutes.")
There are 10 whole hours in 645 minutes.
```

 [!NOTE]
 ### Key Technical Point: Floor Division (`//`) vs. Truncation

* Floor division is not the same as simple truncation (cutting off the decimal). 
* It always **rounds the result down** (towards negative infinity). This distinction is most apparent with negative numbers.

 * For positive numbers, the outcome is the same as truncation:
     * `9 // 2` results in `4`

 * For negative numbers, the result is different:
     * The result of `-9 / 2` is `-4.5`.
     * Rounding *down* from `-4.5` on the number line moves to the left, resulting in `-5`.
     * Therefore, `-9 // 2` results in `-5`, not `-4`.

 To visualize this:
 ```text
 <--|----|----|----|----|----|--
   -6   -5  -4.5 -4   -3   -2   -1
       ^----(round down)
```
---
### ⏰ Practical Example: Calculating Hours and Minutes

By combining floor division (`//`) with the modulo operator (`%`), which provides the remainder of a division, we can elegantly solve common problems like time conversion. 

The following code calculates the whole hours and remaining minutes from a given total number of minutes.

```python
total_minutes = 645

# Get the number of full hours using floor division
hours = total_minutes // 60

# Get the leftover minutes using the modulo operator
remaining_minutes = total_minutes % 60

print(f"{total_minutes} minutes is equal to {hours} hours and {remaining_minutes} minutes.")
Output: 645 minutes is equal to 10 hours and 45 minutes.
```

[!TIP]
### 💡 Choosing the Right Division Operator

 Always make sure to choose the division operator that matches your intended outcome.

 * Use **standard division** (`/`) when you need a **floating-point** result (a number with a decimal). This is essential for most mathematical and scientific calculations where precision is required.

 * Use **floor division** (`//`) when you need an **integer** result (a whole number). This is useful for tasks like calculating grid coordinates, distributing items into full groups, or list indexing.

### 🍎 The Modulo Operator (`%`)

The **modulo operator**, denoted by the percent sign (`%`), works on integers and integer expressions. It performs a division and returns the **remainder** of that division. It's sometimes called the "remainder operator."

 **Analogy: Learning Division**

The modulo operator works just like the long division you learn in school. Imagine you have **7 apples** and want to distribute them equally among **2 baskets**.

* Each basket would receive 3 apples.
* You would have **1 apple remaining**.
 This remaining quantity is exactly what the modulo operator provides.

Here is the analogy in Python code:

```python
apples = 7
baskets = 2
remaining_apples = apples % baskets

print(f"After distributing {apples} apples into {baskets} baskets, there is {remaining_apples} apple left over.")
After distributing 7 apples into 2 baskets, there is 1 apple left over.
```

### Code Example: Floor Division (`//`) and Modulo (`%`)

The following code demonstrates how floor division and the modulo operator work together to deconstruct a division operation.

```python
# Floor division gives the whole number result of a division.
# It answers "How many full times does 5 fit into 13?"
print(13 // 5)

# The modulo operator gives the remainder of a division.
# It answers "What is left over after dividing 13 by 5?"
print(13 % 5)
Output:
2
3
```
#### 🍎 Analogy: Division with Remainders

The modulo operator works just like the long division taught in elementary school. Consider the following scenario:

* You have **7 apples**.
 * You want to distribute them equally among **2 baskets**.

 After distributing them, each basket would contain 3 apples, and you would have **1 apple remaining**.

This remaining quantity is precisely what the modulo operator calculates. In Python, this scenario is expressed as `7 % 2`, which evaluates to `1`.


<img width="750" height="299" alt="appels" src="https://github.com/user-attachments/assets/2f95f687-09f2-4bca-8e5f-66dcfba2d352" />

### ⏰ Practical Application: Converting Minutes to Hours

Let's return to our previous example. Using Python's division and modulo operators, we can easily find the number of whole hours and the remaining minutes from a total of 645 minutes.

The code below demonstrates how each operator contributes to the solution.

```python
# Standard division gives the exact number of hours as a float.
print(645 / 60)

# Floor division gives only the number of WHOLE hours.
print(645 // 60)

# The modulo operator gives the REMAINING minutes.
print(645 % 60)
Outputs:
10.75
10
45
```

##### Putting It All Together
To present this in a human-readable format, we can store the results of the floor division and modulo operations in variables and then combine them using an f-string.
```python
total_minutes = 645

hours = total_minutes // 60
minutes = total_minutes % 60

print(f"Final Result: {hours} hours and {minutes} minutes.")
Final Result: 10 hours and 45 minutes.
```
---
## 🔢 Order of Arithmetic Operators in Python

### Summary of Arithmetic Operators
Here is a final list of the arithmetic operators available in Python:

| Operator | Name | Example | Result |
| :---: | :--- | :--- | :--- |
| `+` | Addition | `2 + 4` | `6` |
| `-` | Subtraction | `10 - 2.5` | `7.5` |
| `*` | Multiplication | `-2 * 123` | `-246` |
| `/` | Division (float result) | `9 / 2` | `4.5` |
| `//`| Floor Division (integer result)| `9 // 2` | `4` |
| `%` | Modulo (remainder) | `9 % 2` | `1` |
| `**`| Exponentiation | `2 ** 3` | `8` |

---

### Operator Precedence (Order of Operations)

In Python, as in mathematics, arithmetic operators follow a specific order of operations. 

1.  **Parentheses** (`()`) are performed first.
2.  **Exponentiation** (`**`) is performed next.
3.  **Multiplication** (`*`), **Division** (`/`, `//`), and **Modulo** (`%`) are performed next.
4.  **Addition** (`+`) and **Subtraction** (`-`) are performed last.

For example, the expression `4 + 2 * 10` equals `24`, not `60`, because multiplication is performed before addition.

```python
# Multiplication has a higher precedence than addition
result = 4 + 2 * 10
print(result)
Output: 24 ## 🔢 Order of Arithmetic Operators in Python
```
## ✨ Modulo Magic

The modulo operator (`%`), which yields the remainder of a division, might seem basic, but it's surprisingly versatile and useful in programming.

---

### Checking for Divisibility

A key use of the modulo operator is to check if one number is perfectly divisible by another. If the remainder of a division is **zero**, it means the dividend is perfectly divisible by the divisor.

For example, `20 % 5` will yield `0`, because 20 divided by 5 leaves no remainder.

```python
# 20 is perfectly divisible by 5, so the remainder is 0.
print(20 % 5)

# 20 is not perfectly divisible by 3, so the remainder is non-zero (it's 2).
print(20 % 3)
Output:
0
2
```
### 👉 Extracting the Right-Most Digit from a Number

* A clever and common use of the **modulo operator** is to extract the right-most digit from any integer. 
* When an integer is divided by **10**, the **remainder** is always the last digit of that number.

The following code demonstrates this. Notice how floor division (`//`) by 10 effectively *removes* the last digit, while the modulo (`%`) operator *isolates* it.

```python
number = 1234

# Floor division by 10 removes the last digit.
print(number // 10)

# Modulo by 10 isolates the last digit.
print(number % 10)
Output:
123
4
```
[!NOTE]
 #### 🤔 Why does this work? The Base-10 Logic

 Our number system is **base-10**, which means any integer can be expressed in terms of its relationship with the number 10.

 * Consider the number `1234`. Mathematically, it's the same as `(123 * 10) + 4`.

* **Floor division** (`// 10`) effectively removes the `+ 4` part and the `* 10` multiplication, giving you the `123` part.

 * **The modulo operator** (`% 10`) finds the remainder after dividing by 10, which is always the `+ 4` part.

 **This technique is fundamental for many algorithms, including reversing a number or checking for palindromes.**

## ✨ Python'da Modulo Operatörü Büyüsü (%)

Modulo operatörü (`%`), ilk bakışta sadece bir bölme işleminden kalanı bulan basit bir araç gibi görünür. Ancak bu operatörün asıl "büyüsü", programlamada karşılaşılan birçok karmaşık problemi zarif ve etkili bir şekilde çözme yeteneğinde yatar. Özellikle **döngüsellik, bölünebilirlik, birim dönüşümü ve desen analizi** gibi konularda temel bir yapı taşıdır.

İşte "Modulo Magic" olarak adlandırılan yaygın kullanım alanları ve teknikleri:

---

### 1. Çift ve Tek Sayı Tespiti

Bu, modülonun en temel ve en yaygın kullanımıdır. Bir sayının `2`'ye bölümünden kalan `0` ise o sayı **çift**, `1` ise **tek**'tir.

```python
def cift_mi_tek_mi(sayi):
    if sayi % 2 == 0:
        return f"{sayi} bir çift sayıdır."
    else:
        return f"{sayi} bir tek sayıdır."

print(cift_mi_tek_mi(100))
print(cift_mi_tek_mi(23))

Output:
100 bir çift sayıdır.
23 bir tek sayıdır.
```

### 2. Döngüsel Davranış ve "Başa Sarma" (Cyclic Behavior)
Modulo, sürekli artan bir sayıyı belirli bir aralıkta tutmak için mükemmeldir.
* Bir değeri n sayısına göre modülosunu aldığınızda, sonuç her zaman 0 ile n-1 arasında kalır. 
* Bu özellik, bir listenin elemanları arasında sürekli dönmek veya saat gibi döngüsel sistemler yaratmak için kullanılır.

 ```python
renkler = ["kırmızı", "yeşil", "mavi"]
# 10. sırada hangi renk gelir?
# 10 % 3 = 1 olduğu için listenin 1. indeksindeki eleman gelir.
print(f"10. sıradaki renk: {renkler[10 % len(renkler)]}")

# Saat örneği: 24 saatlik sistemde 15:00, 12 saatlik sistemde nedir?
saat = 15
print(f"Saat {saat}:00, 12'lik sistemde {saat % 12}:00'dır.")
10. sıradaki renk: yeşil
Saat 15:00, 12'lik sistemde 3:00'dır.
```

### 3. Bir Sayının Son Basamağını Bulma
Onluk sayı sisteminde, bir sayının 10'a bölümünden kalan her zaman o sayının son basamağını (birler basamağını) verir. Bu, sayıları basamaklarına ayırma algoritmalarında temel bir adımdır.

 ```python
sayi = 1234
son_basamak = sayi % 10
print(f"{sayi} sayısının son basamağı: {son_basamak}")
Output:
1234 sayısının son basamağı: 4
```
### 4. Genel Bölünebilirlik Kontrolü
Bir a sayısının, bir b sayısına tam olarak bölünüp bölünmediğini kontrol etmek için modülo kullanılır. Eğer a % b işleminin sonucu 0 ise, a sayısı b'ye tam bölünür.

 ```python
# Bir yılın artık yıl olup olmadığını kontrol etmenin basit bir kuralı
yil = 2024
if yil % 4 == 0:
    print(f"{yil} yılı 4'e tam bölünür.")
Output:
2024 yılı 4'e tam bölünür.
```


### 5. Birim Dönüşümü ve Kalan Hesaplama
Bu teknik, belirli bir toplam değerden daha büyük ve daha küçük birimleri ayıklamak için kullanılır. Tam sayı bölmesi (//) büyük birimi, modülo (%) ise arta kalan küçük birimi verir.

```python
toplam_saniye = 155
dakika = toplam_saniye // 60  # Tam dakikalar
saniye = toplam_saniye % 60   # Geriye kalan saniyeler

print(f"{toplam_saniye} saniye = {dakika} dakika ve {saniye} saniye")
155 saniye = 2 dakika ve 35 saniye
```


### 6. İleri Seviye: 2D Koordinat Hesaplama (Grid Sistemleri)
Oyun geliştirme veya grafik programlama gibi alanlarda, tek boyutlu bir dizideki bir elemanın iki boyutlu bir grid üzerindeki satır ve sütun koordinatlarını bulmak için modülo ve tam sayı bölmesi birlikte kullanılır.

```python
# 10 hücre genişliğinde bir gridde 23. elemanın konumu (0'dan başlayarak)
index = 23
genislik = 10

sutun = index % genislik  # Sütun (Column)
satir = index // genislik # Satır (Row)

print(f"{index}. eleman, {satir}. satır ve {sutun}. sütundadır.")
23. eleman, 2. satır ve 3. sütundadır.
```
---

## 🔄 Type Conversions in Python

Sometimes, it is necessary to convert a value from one data type to another. Python provides simple, built-in functions that allow us to do that. The functions `int()`, `float()`, and `str()` will attempt to convert their arguments into integer, float, and string types, respectively. These are known as **type conversion functions**.

---

### Converting to an Integer with `int()`

The `int()` function can take a floating-point number or a string and turn it into an integer. For floating-point numbers, it discards the decimal portion—a process called **truncation** (it simply cuts off the decimal part without rounding).

Let's see this in action:

#### Example 1: Converting a Float to an Int

```python
float_number = 99.9
integer_number = int(float_number)

print(f"The float value was {float_number}.")
print(f"After conversion to int, the value is {integer_number}.")
Output:
The float value was 99.9.
After conversion to int, the value is 99.
```
---

```python
print(int(3.14))
print(int(3.99))  # This doesn't round to the closest int!
Output:
3
3
```
* Sometimes, type conversions don't work and lead to errors that terminate the program. 
For instance, if you try to change a string to an integer, the string has to be a syntactically legal number, or the conversion will fail:
```python
print(int("2345"))
print(int("Hey123")) # This line will fail
Output:
Line 2: ValueError - invalid literal for int() with base 10: 'Hey123'
```
#### Example: Converting a String to an Int

The `int()` function can also parse a string, provided it contains a whole number.

```python
string_number = "500"
integer_number = int(string_number)

print(f"The string was '{string_number}'. The integer is {integer_number}.")
The string was '500'. The integer is 500.
```
### 📝 Converting to a String with `str()`

The `str()` type conversion function takes any value as its argument and returns a string representation of that value.

> [!CAUTION]
> ### Handling Type Conversion Errors
>
> Sometimes, type conversions don't work and can lead to runtime errors that **terminate the program**. For instance, when converting a string to an integer using `int()`, the string must be a syntactically legal number, or the conversion will fail by raising a `**ValueError**`.
>
> For example, the following code will crash:
>
> ```python
> invalid_string = "hello"
> print("Attempting to convert...")
> number = int(invalid_string) # This line will raise an error
> print("Conversion successful!") # This line will never be reached
> ```
>
> **Program Output and Error:**
>
> ```text
> Attempting to convert...
> Traceback (most recent call last):
>   File "<stdin>", line 3, in <module>
> ValueError: invalid literal for int() with base 10: 'hello'
> ```

#### Example 1: Converting an Integer to a String

```python
number = 123
string_representation = str(number)

# When we print the string, the quotes are not shown
print(f"The value is: {string_representation}")

# But we can verify its type is 'str'
print(f"The type is: {type(string_representation)}")
Output:
The value is: 123
The type is: <class 'str'>
```
#### Example 2: Converting a Float to a String
The same function works for floating-point numbers.

```python
float_number = 99.5
string_representation = str(float_number)

print(f"The value is: {string_representation}")
print(f"The type is: {type(string_representation)}")
```
---

> [!WARNING]
> ### Invalid String to `int()` Conversions
> The `int()` function will raise a `ValueError` if you provide a string that does not represent a whole number. This includes strings with decimals or non-numeric characters.

The following table compares valid and invalid inputs for the `int()` function:

| Input Code | Input Value (String) | Reason | Result |
| :--- | :--- | :--- | :--- |
| `int("500")` | `"500"` | String contains only digits of a whole number. | `500` (Success) |
| `int("500.0")` | `"500.0"` | String represents a float, not an integer. | `ValueError` |
| `int("hello")` | `"hello"` | String contains non-numeric characters. | `ValueError` |

---

> [!TIP]
> ### 💡 Function Calls Are Expressions Too
>
> Remember that when a program runs, **expressions** are simplified or "**evaluated**" into basic values. This rule also applies to function calls.
>
> Consider the following line of code:
>
> ```python
> print(str(17))
> Output: 17
> ```
>
> **Evaluation Steps:**
>
> 1.  Python first evaluates the inner-most expression, which is the function call `str(17)`.
> 2.  This expression simplifies to the string value `"17"`.
> 3.  The original line of code effectively becomes `print("17")`, which Python then executes.


---

### 🏗️ Python'un Aritmetik Operatörleri: İnşaat Şantiyesi Metaforu (Turkish)

Programınızı bir inşaat şantiyesi, sayıları ise inşaat malzemeleriniz (tuğlalar, kum, demir kirişler) olarak düşünün. Operatörler ise bu malzemeleri işlemek için kullandığınız aletler ve makinelerdir.

| Operatör | 👷 İnşaat Metaforu | 📝 Açıklama |
| :---: | :--- | :--- |
| **Sayılar (Numbers)** | 🧱 **Tuğlalar, Kirişler, Kum** | Üzerinde çalıştığımız temel yapı malzemeleridir. |
| `+` | ➕ **Tuğlaları Üst Üste Koymak** | Elimizdeki iki malzeme yığınını birleştirerek daha büyük tek bir yığın oluşturmaktır. |
| `-` | ➖ **Bir Yığından Tuğla Almak** | Malzeme yığınımızdan belirli bir miktarını eksiltmektir. |
| `*` | ✖️ **Bir Sıra Tuğlayı Kopyalamak** | Belirli bir malzeme grubunu (örneğin 3 tuğlalık bir sırayı) birden çok kez kopyalayıp çoğaltmaktır. |
| `/` | 📏 **Bir Kirişi Tam Ölçüyle Kesmek** | Bir demir kirişi, ondalıklı (noktalı) hassasiyetle, tam olarak istenen uzunlukta kesmektir. `9 / 2` sonucu `4.5`'tir. |
| `**`| 🏢 **Katları Üst Üste Çıkmak** | Bu, basit bir kopyalama değil, üssel bir büyümedir. `2 ** 3`, 2 birimlik bir temelin üzerine 3 kat çıkarak dev bir yapı oluşturması gibidir. |
| `//`| 📦 **Bir Alana Kaç Tam Palet Sığar?** | Elimizdeki alana, belirli boyuttaki paletlerden kaç tanesinin *tam olarak* sığacağını hesaplamaktır. `9 // 2` ile **4** tam palet sığar. |
| `%` | 📐 **Paletler Sığdıktan Sonra Kalan Boşluk** | Paletleri yerleştirdikten sonra artan, kullanılamayan alanı veya malzemeyi hesaplamaktır. `9 % 2` işleminden sonra **1** birimlik boşluk kalır. |
| **İşlem Önceliği** | 📋 **Mimarın İnşaat Planı (PEMDAS)** | Şantiyede işler rastgele yapılmaz. Plana göre önce temel (parantezler), sonra ana iskelet (çarpma/bölme) ve en son ince işçilik (toplama/çıkarma) yapılır. |
| `()`| ❗️ **"ÖNCE BURAYI YAP!" Notu** | Mimarın veya ustabaşının, plana "normal sırası ne olursa olsun, önce bu bölgeyi bitirin" diye özel bir not bırakmasıdır. Bu not, standart inşaat planını geçersiz kılar. |





 <img width="100" height="300" alt="Minik Seytan" src="https://github.com/user-attachments/assets/c87c8f3d-4b44-4da5-9c04-2026349a5a2a" />






