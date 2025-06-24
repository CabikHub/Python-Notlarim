# Python [If-Controls]

---

# 🚦 Python'da Koşul Blokları (if, elif, else)

Koşul blokları, programlarımızın karar vermesini ve belirli şartlar sağlandığında belirli kodları çalıştırmasını, sağlanmadığında ise başka kodları çalıştırmasını sağlayan temel kontrol mekanizmalarıdır. Programın akışını bu bloklarla yönetiriz.

---

### 🧱 Koşulların Temeli: Operatörler

`if` bloklarının çalışması, `True` veya `False` sonucu üreten **Boolean** ifadelerine bağlıdır. Bu ifadeleri oluşturmak için karşılaştırma, mantıksal ve üyelik operatörlerini kullanırız.

| Operatör Tipi | Operatörler | Anlamları |
| --- | --- | --- |
| **Karşılaştırma** | `==`, `!=`, `>`, `<`, `>=`, `<=` | Eşit mi, Eşit değil mi, Büyük/Küçük mü, Büyük/Küçük veya Eşit mi |
| **Mantıksal** | `and`, `or`, `not` | Ve (her iki koşul da doğru olmalı), Veya (koşullardan en az biri doğru olmalı), Değil (sonucu tersine çevirir) |
| **Üyelik** | `in`, `not in` | İçinde var mı, İçinde yok mu |

```python
# Karşılaştırma Örneği
x = 10
y = 8
print(x > y)  # Çıktı: True

# Mantıksal Örnek
print(x > 5 and y < 10) # Çıktı: True

# Üyelik Örneği
my_list = [10, 20, 30]
print(10 in my_list) # Çıktı: True

```

### 🔍 Üyelik Operatörü (`in`) ile Kontrol

`in` operatörü, bir elemanın bir koleksiyon (liste, sözlük, küme vb.) içinde olup olmadığını kontrol eder.

```python
# Listede üyelik kontrolü
print(10 in [10, 20, 30]) # Çıktı: True

# Sözlükte Değer (Value) Kontrolü
my_dictionary = {"a": 10, "b": 20, "c": 30}
print(10 in my_dictionary.values()) # Çıktı: True

# Sözlükte Anahtar (Key) Kontrolü
print("a" in my_dictionary.keys()) # Çıktı: True

```

---

### 1. Temel `if` Yapısı

Bir koşulun sonucu `True` ise, `if` bloğunun altındaki girintili (indentation) kodlar çalışır. Eğer sonuç `False` ise, o blok tamamen atlanır.

> DİKKAT: Python'da girintiler (kodun başındaki boşluklar) çok önemlidir. if bloğuna ait kodlar mutlaka bir Tab boşluğu içeride olmalıdır.
> 

```python
my_superhero = "Batman"

if my_superhero == "Batman":
    # Bu blok sadece koşul True ise çalışır
    print("Doğru tahmin, kahraman Batman!")
    print("Emirhan Çabık")

# Bu satır if bloğunun dışında olduğu için her zaman çalışır
print("Koşul bloğu sona erdi.")

```

*Output:*`Doğru tahmin, kahraman Batman!Emirhan ÇabıkKoşul bloğu sona erdi.`

---

### 2\. `if-elif-else` Zinciri

Birden fazla koşulu sırayla kontrol etmek için `if`, `elif` (else if'in kısaltması) ve `else` yapısını kullanırız. Python, doğru olan ilk koşulu bulduğu an o bloğu çalıştırır ve zincirin geri kalanını kontrol etmeden atlar.

- `if`: İlk kontrol edilen koşul.
- `elif`: `if` yanlışsa kontrol edilen ikinci, üçüncü, ... koşullar.
- `else`: Yukarıdaki koşulların **hiçbiri** doğru değilse çalışan "varsayılan" bloktur.

<!-- end list -->

```python
my_age = int(input("Yaşınızı Giriniz: "))

if my_age <= 18:
    print("Yaşınız 18 veya daha küçük.")
elif my_age > 18 and my_age <= 40:
    print("Yaşınız 18 ile 40 arasında.")
else:
    print("Yaşınız 40'tan büyüktür.")

```

---

### ✨ Olmazsa Olmaz Ekstra Örnekler

### İç İçe `if` Blokları

Bir `if` bloğunun içine başka bir `if` bloğu yazabilirsiniz. Bu, bir koşul sağlandıktan sonra başka bir alt koşulu kontrol etmek için kullanılır.

```python
# Kullanıcı giriş yapmış mı ve admin mi?
is_logged_in = True
is_admin = False

if is_logged_in == True:
    print("Hoş geldin! Giriş yapıldı.")
    if is_admin == True:
        print("Admin paneline yönlendiriliyorsunuz...")
    else:
        print("Admin yetkiniz bulunmuyor.")
else:
    print("Lütfen önce giriş yapın.")

```

*Output:*`Hoş geldin! Giriş yapıldı.Admin yetkiniz bulunmuyor.`

### "Truthiness" (Doğruluk Değeri) Kavramı

Python'da sadece `True` ve `False` değil, diğer veri tipleri de mantıksal olarak değerlendirilir.

- **`False` kabul edilenler:** Boş listeler `[]`, boş metinler `""`, `0` sayısı ve `None` değeri.
- **`True` kabul edilenler:** Dolu listeler, dolu metinler ve `0` dışındaki tüm sayılar.

Bu özellik, kodumuzu kısaltmamızı sağlar.

```python
my_shopping_list = ["Elma", "Ekmek"]

# UZUN YÖNTEM
if len(my_shopping_list) > 0:
    print("Alışveriş listesi boş değil.")

# KISA ve PYTHONIC YÖNTEM
if my_shopping_list: # Liste dolu olduğu için burası True kabul edilir
    print("Alışveriş listesi boş değil.")

```

*Her iki örnek de aynı çıktıyı verir:* `Alışveriş listesi boş değil.`

# For ENG

---

# 🚦 Conditional Blocks in Python (if, elif, else)

Conditional blocks are fundamental control mechanisms that allow our programs to make decisions, executing certain code when specific conditions are met, and other code when they are not. We manage the flow of the program with these blocks.

---

### 🧱 The Foundation of Conditions: Operators

The operation of `if` blocks depends on Boolean expressions that produce a result of `True` or `False`. We use comparison, logical, and membership operators to create these expressions.

| Operator Type | Operators | Meanings |
| --- | --- | --- |
| **Comparison** | `==`, `!=`, `>`, `<`, `>=`, `<=` | Equal to, Not equal to, Greater/Less than, Greater/Less than or equal to |
| **Logical** | `and`, `or`, `not` | And (both conditions must be true), Or (at least one condition must be true), Not (reverses the result) |
| **Membership** | `in`, `not in` | Is it in, Is it not in |

```python
# Comparison Example
x = 10
y = 8
print(x > y)  # Output: True

# Logical Example
print(x > 5 and y < 10) # Output: True

# Membership Example
my_list = [10, 20, 30]
print(10 in my_list) # Output: True

```

### 🔍 Checking with the Membership Operator (`in`)

The `in` operator checks whether an element exists within a collection (list, dictionary, set, etc.).

```python
# Membership check in a list
print(10 in [10, 20, 30]) # Output: True

# Checking for a Value in a dictionary
my_dictionary = {"a": 10, "b": 20, "c": 30}
print(10 in my_dictionary.values()) # Output: True

# Checking for a Key in a dictionary
print("a" in my_dictionary.keys()) # Output: True

```

---

### 1. Basic `if` Structure

If the result of a condition is `True`, the indented code under the `if` block is executed. If the result is `False`, that block is skipped entirely.

> ATTENTION: In Python, indentation (the spaces at the beginning of the code) is very important. The code belonging to an if block must be indented, typically by one Tab space.
> 

```python
my_superhero = "Batman"

if my_superhero == "Batman":
    # This block only runs if the condition is True
    print("Correct guess, the hero is Batman!")
    print("Emirhan Çabık")

# This line is outside the if block, so it always runs
print("Conditional block has ended.")

```

*Output:*`Correct guess, the hero is Batman!Emirhan ÇabıkConditional block has ended.`

---

### 2. The `if-elif-else` Chain

To check multiple conditions sequentially, we use the `if`, `elif` (short for else if), and `else` structure. Python executes the block for the first `True` condition it finds and then skips the rest of the chain.

- `if`: The first condition to be checked.
- `elif`: The second, third, ... conditions to be checked if the `if` is false.
- `else`: The "default" block that runs if **none** of the above conditions are true.

<!-- end list -->

```python
my_age = int(input("Enter your age: "))

if my_age <= 18:
    print("Your age is 18 or younger.")
elif my_age > 18 and my_age <= 40:
    print("Your age is between 18 and 40.")
else:
    print("Your age is greater than 40.")

```

---

### ✨ Must-Have Extra Examples

### Nested `if` Blocks

You can write another `if` block inside an `if` block. This is used to check a secondary condition after a primary condition is met.

```python
# Is the user logged in and are they an admin?
is_logged_in = True
is_admin = False

if is_logged_in == True:
    print("Welcome! Logged in.")
    if is_admin == True:
        print("Redirecting to admin panel...")
    else:
        print("You do not have admin privileges.")
else:
    print("Please log in first.")

```

*Output:*`Welcome! Logged in.You do not have admin privileges.`

### The Concept of "Truthiness"

In Python, not only `True` and `False`, but other data types are also evaluated logically.

- **Considered `False`:** Empty lists `[]`, empty strings `""`, the number `0`, and the `None` value.
- **Considered `True`:** Non-empty lists, non-empty strings, and all numbers other than `0`.

This feature allows us to shorten our code.

```python
my_shopping_list = ["Apple", "Bread"]

# LONG METHOD
if len(my_shopping_list) > 0:
    print("The shopping list is not empty.")

# SHORT and PYTHONIC METHOD
if my_shopping_list: # Since the list is not empty, this is considered True
    print("The shopping list is not empty.")

```

*Both examples produce the same output:* `The shopping list is not empty.`