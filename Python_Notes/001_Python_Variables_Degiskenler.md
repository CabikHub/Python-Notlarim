# Python -  [Variables]

---

# 🐍 Python'da Sayılar ve Matematiksel İşlemler

Bu not, Python programlama dilindeki en temel yapı taşlarından olan sayılar, değişkenler ve matematiksel operatörler üzerine odaklanmaktadır.

---

## 🔢 Temel Matematiksel Operatörler

Python, temel matematiksel hesaplamalar için sezgisel operatörler sunar.

- **Toplama `+`**
    
    ```python
    3 + 5
    # Çıktı: 8
    
    ```
    
- **Çıkarma**
    
    ```python
    10 - 100
    # Çıktı: -90
    
    ```
    
- **Çarpma**
    
    ```python
    4 * 3
    # Çıktı: 12
    
    ```
    
- **Bölme `/`**
    
    ```python
    900 / 4
    # Çıktı: 225.0
    
    ```
    
    > 💡 Önemli Not: Python'da bölme işlemi (/) yapıldığında, sonuç tam sayı olsa bile her zaman ondalıklı bir sayı (float) olarak döner. Örneğin, 40 / 4 işleminin sonucu 10 değil, 10.0'dır.
    > 

---

## 📦 Değişkenler (Variables)

Değişkenler, verileri (sayılar, metinler vb.) saklamak için kullandığımız isimlendirilmiş kaplardır.

- Bir değişkene değer atamak için `=` operatörü kullanılır.
    
    ```python
    # 'age' isminde bir değişken oluşturup içine 50 değerini atıyoruz.
    age = 50
    
    ```
    
- Değişkenler, atandıkları değeri temsil eder ve matematiksel işlemlerde kullanılabilir.
    
    ```python
    age * 5
    # Çıktı: 250
    
    age / 2
    # Çıktı: 25.0
    
    ```
    
- Değişkenlerin değeri sonradan değiştirilebilir. Python her zaman en son atanan değeri baz alır.
    
    ```python
    x = 10
    x = 20
    x + 10
    # Çıktı: 30 (Çünkü x'in son değeri 20'dir)
    
    ```
    

> ✍️ İsimlendirme Stilleri: Kod yazarken değişkenleri isimlendirmek için genel kabul görmüş bazı stiller vardır:
> 
> - `camelCase`: `myFloat`
> - `snake_case`: `my_float`
> Python topluluğunda genellikle **snake\_case** kullanımı tercih edilir.

---

## 📊 Veri Tipleri (Data Types)

Python'da her verinin bir tipi vardır. Sayılar için en yaygın iki veri tipi `int` ve `float`'tır. Bir verinin tipini öğrenmek için `type()` fonksiyonu kullanılır.

### Tamsayılar (Integer - `int`)

Pozitif veya negatif, ondalık kısmı olmayan sayılardır.

```python
type(10)      # Çıktı: int
type(-1000)   # Çıktı: int

```

### Ondalıklı Sayılar (Float)

Ondalık noktası olan sayılardır.

```python
# 'pi' adında bir float değişkeni
pi = 3.14

type(3.14)    # Çıktı: float
type(pi)      # Çıktı: float

```

- Farklı tiplerdeki sayılarla işlem yapıldığında, sonuç genellikle daha kapsayıcı olan `float` tipinde olur.
    
    ```python
    x = -100     # Bu bir integer
    pi = 3.14    # Bu bir float
    x + pi       # int + float -> float
    # Çıktı: -96.86
    
    ```
    

---

## ✨ Diğer Önemli Operatörler ve Kavramlar

### Üs Alma (`*`)

Bir sayının kuvvetini (üssünü) almak için kullanılır.

```python
# 2'nin 5. kuvveti
2 ** 5
# Çıktı: 32

```

### Mod Alma (`%`)

Bir sayının başka bir sayıya bölümünden kalanı verir.

```python
# 10'un 3'e bölümünden kalan
10 % 3
# Çıktı: 1

# 10'un 2'ye bölümünden kalan (Çift sayı kontrolü için harikadır)
10 % 2
# Çıktı: 0

```

### 🧠 İşlem Önceliği

Python, matematikteki işlem önceliği kurallarını (Çarpma/Bölme önce, Toplama/Çıkarma sonra) takip eder.

```python
# Önce 10 * 2 (çarpma) yapılır, sonra 2'den çıkarılır.
2 - 10 * 2
# Çıktı: -18

```

# For ENG

---

# 🐍 Numbers and Mathematical Operations in Python

This note focuses on one of the most fundamental building blocks in the Python programming language: numbers, variables, and mathematical operators.

---

## 🔢 Basic Mathematical Operators

Python provides intuitive operators for basic arithmetic calculations.

- **Addition `+`**
    
    ```python
    3 + 5
    # Output: 8
    
    ```
    
- **Subtraction**
    
    ```python
    10 - 100
    # Output: -90
    
    ```
    
- **Multiplication**
    
    ```python
    4 * 3
    # Output: 12
    
    ```
    
- **Division `/`**
    
    ```python
    900 / 4
    # Output: 225.0
    
    ```
    
    > 💡 Note: When performing division (/) in Python, the result is always a decimal number (float), even if the result is a whole number. For example, 40 / 4 returns 10.0, not 10.
    > 

---

## 📦 Variables

Variables are named containers used to store data (numbers, strings, etc.).

- Use the `=` operator to assign a value to a variable.
    
    ```python
    # We create a variable named 'age' and assign it the value 50.
    age = 50
    
    ```
    
- Variables represent the value they are assigned and can be used in arithmetic operations.
    
    ```python
    age * 5
    # Output: 250
    
    age / 2
    # Output: 25.0
    
    ```
    
- The value of a variable can be changed later. Python always uses the most recently assigned value.
    
    ```python
    x = 10
    x = 20
    x + 10
    # Output: 30 (Because the latest value of x is 20)
    
    ```
    

> ✍️ Naming Styles: When writing code, there are some commonly accepted styles for naming variables:
> 
> - `camelCase`: `myFloat`
> - `snake_case`: `my_float`
>     
>     The Python community generally prefers the **snake_case** style.
>     

---

## 📊 Data Types

In Python, every piece of data has a type. For numbers, the two most common data types are `int` and `float`. You can find out the type of a value using the `type()` function.

### Integers (`int`)

Positive or negative whole numbers without decimal points.

```python
type(10)      # Output: int
type(-1000)   # Output: int

```

### Floating Point Numbers (`float`)

Numbers that have a decimal point.

```python
# A float variable named 'pi'
pi = 3.14

type(3.14)    # Output: float
type(pi)      # Output: float

```

- When performing operations with mixed types, the result is typically of the more inclusive type: `float`.
    
    ```python
    x = -100     # This is an integer
    pi = 3.14    # This is a float
    x + pi       # int + float -> float
    # Output: -96.86
    
    ```
    

---

## ✨ Other Important Operators and Concepts

### Exponentiation (`*`)

Used to raise a number to a power.

```python
# 2 raised to the 5th power
2 ** 5
# Output: 32

```

### Modulo (`%`)

Gives the remainder of a division.

```python
# The remainder of 10 divided by 3
10 % 3
# Output: 1

# The remainder of 10 divided by 2 (great for checking even numbers)
10 % 2
# Output: 0

```

### 🧠 Order of Operations

Python follows standard math rules for order of operations (Multiplication/Division before Addition/Subtraction).

```python
# First 10 * 2 (multiplication), then subtract from 2
2 - 10 * 2
# Output: -18

```

---