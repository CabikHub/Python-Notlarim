# Python [Loops]

---

# 🔄 Python'da Döngüler (for & while)

Döngüler, bir kod bloğunu belirli bir koşul sağlandığı sürece veya bir koleksiyondaki her bir eleman için tekrar tekrar çalıştırmamızı sağlayan temel programlama yapılarıdır. Bu, kod tekrarını önler ve işlemleri otomatikleştirir.

---

## 🔂 `for` Döngüsü: Koleksiyonlar Üzerinde Gezinme

`for` döngüsü, bir koleksiyonun (liste, demet, string, sözlük vb.) her bir elemanını sırayla gezip her biri için bir işlem yapmak istediğimizde kullanılır.

### 🔹 Liste ve String Üzerinde Gezinme

```python
my_list = [10, 20, 30, 40, 50]

for num in my_list:
    print(f"Sıradaki sayı: {num}")

```

```python
my_string = "emirhan"
for letter in my_string:
    print(letter)

```

### 🔹 Sözlük Üzerinde Gezinme (`.items()`)

```python
my_dictionary = {"a": 1, "b": 2, "c": 3}

for key, value in my_dictionary.items():
    print(f"Anahtar: {key}, Değer: {value}")

```

### 🔹 `range()` Fonksiyonu ile Sayılı İşlem

```python
for x in range(5):
    print(x)

```

---

## ⏳ `while` Döngüsü: Koşula Bağlı Tekrar

`while` döngüsü, belirtilen koşul `True` olduğu sürece kod bloğu çalışır.

### ❗ Sonsuz Döngülere Dikkat:

```python
x = 0

while x < 5:
    print(f"x'in güncel değeri: {x}")
    x += 1

```

---

## ⚙️ Döngü Kontrol İfadeleri

### 🔹 `break` (Döngüyü Kır)

```python
for number in [10, 20, 30, 40]:
    if number == 30:
        break
    print(number)

```

### 🔹 `continue` (Adımı Atlıyor)

```python
for number in [1, 2, 3, 4, 5, 6]:
    if number % 2 == 0:
        continue
    print(f"Tek sayı: {number}")

```

### 🔹 `pass` (Yer Tutucu)

```python
for number in [1, 2, 3]:
    pass

```

### 🔹 `else` ile `for` / `while`

```python
for i in range(3):
    print(i)
else:
    print("Döngü tamamlandı.")

```

---

## 🚀 Bonus: List Comprehension

```python
my_list = [10, 20, 30]
new_list = [element * 5 for element in my_list]
print(new_list)

```

---

## 🧪 Seviye Seviye Örnekler

### ✅ Kolay `for`

```python
for harf in "Python":
    print(harf)

```

### ✅ Kolay `while`

```python
sayi = 0
while sayi < 5:
    print(sayi)
    sayi += 1

```

### 🟡 Orta `for`

```python
sayilar = [10, 20, 30, 40]
for sayi in sayilar:
    print(sayi / 5 * 2)

```

### 🟡 Orta `while`

```python
sayi = 10
while sayi >= 0:
    print(sayi)
    sayi -= 2

```

### 🔴 Zor `for`

```python
liste = [[1, 2], [3, 4], [5, 6]]
for alt_liste in liste:
    for eleman in alt_liste:
        print(eleman * 10)

```

### 🔴 Zor `while`

```python
liste = [1, 3, 5, 7, 9]
index = 0
while index < len(liste):
    if liste[index] % 3 == 0:
        print(f"{liste[index]} 3'e bölünebilir.")
    index += 1

```

---

## 🔍 Ekstra Örnekler

### 🔁 Değer Arttırma ile while

```python
p = 0
while p < 20:
    print(f"value of p: {p}")
    p += 1

```

![image.png](image.png)

### 🔁 Liste Elemanı Kontrolü

```python
last_list = [10, 20, 30, 40, 50]

while 20 in last_list:
    print("20 in last_list")
    last_list.pop()

```

---

✅ **Not:** `for` döngüsü belirli bir sırada işlemler için uygundur. `while` ise daha esnek, koşul bazlı işlemlerde tercih edilir.

# For ENG

---

# 🔄 Loops in Python (for & while)

Loops are fundamental programming structures that allow a block of code to run repeatedly either while a condition is met or for each item in a collection. This avoids code repetition and automates processes.

---

## 🔂 `for` Loop: Iterating Over Collections

The `for` loop is used to iterate over each element in a collection (like list, tuple, string, dictionary, etc.) and perform an operation for each one.

### 🔹 Iterating Over Lists and Strings

```python
my_list = [10, 20, 30, 40, 50]

for num in my_list:
    print(f"Next number: {num}")

```

```python
my_string = "emirhan"
for letter in my_string:
    print(letter)

```

### 🔹 Iterating Over Dictionaries (`.items()`)

```python
my_dictionary = {"a": 1, "b": 2, "c": 3}

for key, value in my_dictionary.items():
    print(f"Key: {key}, Value: {value}")

```

### 🔹 Looping with `range()`

```python
for x in range(5):
    print(x)

```

---

## ⏳ `while` Loop: Repeat While a Condition is True

The `while` loop keeps running as long as the specified condition is `True`.

### ❗ Watch Out for Infinite Loops:

```python
x = 0

while x < 5:
    print(f"Current value of x: {x}")
    x += 1

```

---

## ⚙️ Loop Control Statements

### 🔹 `break` (Exit the Loop)

```python
for number in [10, 20, 30, 40]:
    if number == 30:
        break
    print(number)

```

### 🔹 `continue` (Skip the Current Iteration)

```python
for number in [1, 2, 3, 4, 5, 6]:
    if number % 2 == 0:
        continue
    print(f"Odd number: {number}")

```

### 🔹 `pass` (Do Nothing)

```python
for number in [1, 2, 3]:
    pass

```

### 🔹 `else` with `for` / `while`

```python
for i in range(3):
    print(i)
else:
    print("Loop completed.")

```

---

## 🚀 Bonus: List Comprehension

```python
my_list = [10, 20, 30]
new_list = [element * 5 for element in my_list]
print(new_list)

```

---

## 🧪 Examples by Difficulty Level

### ✅ Easy `for`

```python
for letter in "Python":
    print(letter)

```

### ✅ Easy `while`

```python
number = 0
while number < 5:
    print(number)
    number += 1

```

### 🟡 Medium `for`

```python
numbers = [10, 20, 30, 40]
for number in numbers:
    print(number / 5 * 2)

```

### 🟡 Medium `while`

```python
number = 10
while number >= 0:
    print(number)
    number -= 2

```

### 🔴 Hard `for`

```python
nested_list = [[1, 2], [3, 4], [5, 6]]
for sublist in nested_list:
    for item in sublist:
        print(item * 10)

```

### 🔴 Hard `while`

```python
numbers = [1, 3, 5, 7, 9]
index = 0
while index < len(numbers):
    if numbers[index] % 3 == 0:
        print(f"{numbers[index]} is divisible by 3.")
    index += 1

```

---

## 🔍 Extra Examples

### 🔁 Incrementing with `while`

```python
p = 0
while p < 20:
    print(f"value of p: {p}")
    p += 1

```

### 🔁 Checking for an Element in a List

```python
last_list = [10, 20, 30, 40, 50]

while 20 in last_list:
    print("20 in last_list")
    last_list.pop()

```

---

✅ **Note:** Use `for` loops for fixed-sequence operations. Use `while` for more flexible, condition-based tasks.