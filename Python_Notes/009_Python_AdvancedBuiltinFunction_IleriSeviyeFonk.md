# Python [AdvancedBuiltinFunction]

# ✨ Python'da İleri Düzey Fonksiyonlar ve Döngü Teknikleri

Bu not, Python'da döngüleri daha güçlü ve verimli hale getiren dahili fonksiyonları ve modern teknikleri ele almaktadır.

---

### 1️⃣ `range()` Fonksiyonu: Sayı Dizileri Üretme

`range()`, belirli bir aralıkta sıralı sayılar üretmek için kullanılır. Özellikle `for` döngülerinde, bir işlemi belirli sayıda tekrarlamak için idealdir.

### ✅ Kolay Örnek: 0'dan Başlayan Döngü

`range(N)` yazdığınızda, 0'dan başlar ve N'e kadar (N dahil değil) birer birer sayar.

```python
# 0'dan 5'e kadar (5 hariç) olan sayıları yazdırır
for sayi in range(5):
    print(sayi)
# Çıktı:
# 0
# 1
# 2
# 3
# 4

```

### 🟡 Orta Örnek: Başlangıç ve Bitiş Belirtme

`range(baslangic, bitis)` formatıyla belirli bir aralıkta sayılar üretebilirsiniz.

```python
# 5'ten 10'a kadar (10 hariç) olan sayıları listeye çevirir
my_list = list(range(5, 10))
print(my_list)
# Çıktı: [5, 6, 7, 8, 9]

```

### 🔴 Zor Örnek: Adım Boyutu Belirleme (Geriye Sayma)

`range(baslangic, bitis, adim)` formatıyla sayıların kaçar kaçar artacağını veya azalacağını belirleyebilirsiniz.

```python
# 10'dan başlayıp 0'a kadar (0 hariç) 2'şer azalarak sayar
for sayi in range(10, 0, -2):
    print(sayi)
# Çıktı:
# 10
# 8
# 6
# 4
# 2

```

---

### 2️⃣ `enumerate()` Fonksiyonu: İndeks ve Değeri Birlikte Almak

Bir koleksiyon üzerinde dönerken hem elemanın kendisini hem de onun indeksini aynı anda almak için kullanılır. Bu, `range(len(liste))` kullanmaktan çok daha "Pythonic" (Python'a özgü şık) bir yöntemdir.

### ✅ Kolay Örnek: Temel Kullanım

`enumerate`, her adımda `(indeks, değer)` şeklinde bir demet (tuple) döndürür.

```python
my_list = [20, 30, 40]
for element in enumerate(my_list):
    print(element)
# Çıktı:
# (0, 20)
# (1, 30)
# (2, 40)

```

### 🟡 Orta Örnek: Tuple Unpacking (Demetleri Ayrıştırma)

Döngü içinde indeks ve değeri ayrı değişkenlere atayarak çok daha kullanışlı hale getirebiliriz.

```python
my_list = [20, 30, 40]
for index, value in enumerate(my_list):
    print(f"İndeks: {index}, Değer: {value}")
# Çıktı:
# İndeks: 0, Değer: 20
# İndeks: 1, Değer: 30
# İndeks: 2, Değer: 40

```

### 🔴 Zor Örnek: Numaralandırmaya Farklı Sayıdan Başlama

`start` parametresi ile indekslemenin 0 yerine istediğiniz bir sayıdan başlamasını sağlayabilirsiniz.

```python
my_list = ["Elma", "Armut", "Çilek"]
for index, meyve in enumerate(my_list, start=1):
    print(f"{index}. Meyve: {meyve}")
# Çıktı:
# 1. Meyve: Elma
# 2. Meyve: Armut
# 3. Meyve: Çilek

```

---

### 3️⃣ `zip()` Fonksiyonu: Listeleri Birleştirme

Birden fazla listeyi, aynı indeksteki elemanları bir araya getirerek tek bir yapıya dönüştürür. Sonuç, demetlerden (tuple) oluşan bir koleksiyondur.

### ✅ Kolay Örnek: İki Listeyi "Fermuarlamak"

```python
food_list = ["apple", "banana", "melon"]
calories_list = [100, 150, 200]

zipped_list = list(zip(food_list, calories_list))
print(zipped_list)
# Çıktı: [('apple', 100), ('banana', 150), ('melon', 200)]

```

### 🟡 Orta Örnek: Üç Listeyi Birleştirmek

```python
food_list = ["apple", "banana", "melon"]
calories_list = [100, 150, 200]
day_list = ["monday", "tuesday", "wednesday"]

zipped_list = list(zip(food_list, calories_list, day_list))
print(zipped_list)
# Çıktı: [('apple', 100, 'monday'), ('banana', 150, 'tuesday'), ('melon', 200, 'wednesday')]

```

### 🔴 Zor Örnek: `zip` ile Döngü Kurmak

```python
for yemek, kalori in zip(food_list, calories_list):
    print(f"{yemek.capitalize()} {kalori} kaloridir.")
# Çıktı:
# Apple 100 kaloridir.
# Banana 150 kaloridir.
# Melon 200 kaloridir.

```

---

### 4️⃣ `random` Modülü: Rastgele İşlemler

Rastgele sayılar üretmek veya listeleri karıştırmak gibi işlemler için `random` modülünü kullanırız.

### ✅ `randint()` ile Rastgele Sayı Üretme

`randint(a, b)` fonksiyonu, `a` ve `b` (dahil) arasında rastgele bir tam sayı üretir.

```python
from random import randint
# 0 ile 100 arasında rastgele bir sayı üretir
print(randint(0, 100))

```

> 💡 Önemli İpucu: Bir listeden rastgele bir eleman seçerken, en son indeks len(liste) - 1 olduğu için randint(0, len(my_list) - 1) kullanmak en doğrusudur. Aksi takdirde IndexError hatası alabilirsiniz.
> 

### 🟡 `shuffle()` ile Liste Karıştırma

`shuffle()` fonksiyonu, bir listenin elemanlarını **yerinde** (kalıcı olarak) karıştırır.

```python
from random import shuffle
my_list = [10, 20, 30, 40, 50, 60, 70]
shuffle(my_list)
print(my_list)
# Çıktı (Örnek): [40, 10, 70, 50, 20, 60, 30]

```

---

### 5️⃣ List Comprehension (Liste Üretkenliği)

Döngü kullanarak yeni bir liste oluşturmanın çok daha kısa, okunaklı ve verimli bir yoludur.

### ✅ Kolay Örnek: Basit Bir Kopyalama

Klasik `for` döngüsüne şık bir alternatif.

```python
# Klasik Yöntem
new_list = []
my_string = "metallica"
for element in my_string:
    new_list.append(element)
print(new_list)
# Çıktı: ['m', 'e', 't', 'a', 'l', 'l', 'i', 'c', 'a']

# List Comprehension Yöntemi
new_list_comp = [element for element in my_string]
print(new_list_comp)
# Çıktı: ['m', 'e', 't', 'a', 'l', 'l', 'i', 'c', 'a']

```

### 🟡 Orta Örnek: Koşul Ekleme (`if`)

Sadece belirli bir koşulu sağlayan elemanları yeni listeye dahil edebilirsiniz.

```python
number_list = [10, 21, 30, 45, 50]
# Sadece çift sayıları al
cift_sayilar = [num for num in number_list if num % 2 == 0]
print(cift_sayilar)
# Çıktı: [10, 30, 50]

```

### 🔴 Zor Örnek: Koşullu Değer Atama (`if/else`)

Her eleman için koşula bağlı olarak farklı bir değer atayabilirsiniz.

```python
number_list = [1, 2, 3, 4, 5]
# Çift ise kendisini, tek ise 'Tek Sayı' metnini listeye ekle
yeni_liste = [num if num % 2 == 0 else "Tek Sayı" for num in number_list]
print(yeni_liste)
# Çıktı: ['Tek Sayı', 2, 'Tek Sayı', 4, 'Tek Sayı']

```

# For ENG

# ✨ Advanced Built-in Functions and Loop Techniques in Python

This note covers the built-in functions and modern techniques that make loops more powerful and efficient in Python.

---

### 1️⃣ `range()` Function: Generating Number Sequences

`range()` is used to generate a sequence of numbers within a specific interval. It is ideal for repeating an operation a specific number of times, especially in `for` loops.

### ✅ Easy Example: Loop Starting from 0

When you write `range(N)`, it starts from 0 and counts up to N (not including N), one by one.

```python
# Prints numbers from 0 to 5 (not including 5)
for number in range(5):
    print(number)
# Output:
# 0
# 1
# 2
# 3
# 4

```

### 🟡 Medium Example: Specifying Start and End

You can generate numbers in a specific range with the `range(start, stop)` format.

```python
# Converts numbers from 5 to 10 (not including 10) into a list
my_list = list(range(5, 10))
print(my_list)
# Output: [5, 6, 7, 8, 9]

```

### 🔴 Hard Example: Specifying Step Size (Counting Backwards)

With the `range(start, stop, step)` format, you can specify how much the numbers should increase or decrease.

```python
# Counts down from 10 to 0 (not including 0), decreasing by 2
for number in range(10, 0, -2):
    print(number)
# Output:
# 10
# 8
# 6
# 4
# 2

```

---

### 2️⃣ `enumerate()` Function: Getting Index and Value Together

It is used to get both the element itself and its index simultaneously while iterating over a collection. This is a much more "Pythonic" way than using `range(len(my_list))`.

### ✅ Easy Example: Basic Usage

`enumerate` returns a tuple of `(index, value)` at each step.

```python
my_list = [20, 30, 40]
for element in enumerate(my_list):
    print(element)
# Output:
# (0, 20)
# (1, 30)
# (2, 40)

```

### 🟡 Medium Example: Tuple Unpacking

We can make it much more useful by assigning the index and value to separate variables within the loop.

```python
my_list = [20, 30, 40]
for index, value in enumerate(my_list):
    print(f"Index: {index}, Value: {value}")
# Output:
# Index: 0, Value: 20
# Index: 1, Value: 30
# Index: 2, Value: 40

```

### 🔴 Hard Example: Starting Enumeration from a Different Number

With the `start` parameter, you can have the indexing begin at a number of your choice instead of 0.

```python
my_list = ["Apple", "Pear", "Strawberry"]
for index, fruit in enumerate(my_list, start=1):
    print(f"{index}. Fruit: {fruit}")
# Output:
# 1. Fruit: Apple
# 2. Fruit: Pear
# 3. Fruit: Strawberry

```

---

### 3️⃣ `zip()` Function: Combining Lists

It combines multiple lists into a single structure by pairing up elements at the same index. The result is a collection of tuples.

### ✅ Easy Example: "Zipping" Two Lists

```python
food_list = ["apple", "banana", "melon"]
calories_list = [100, 150, 200]

zipped_list = list(zip(food_list, calories_list))
print(zipped_list)
# Output: [('apple', 100), ('banana', 150), ('melon', 200)]

```

### 🟡 Medium Example: Combining Three Lists

```python
food_list = ["apple", "banana", "melon"]
calories_list = [100, 150, 200]
day_list = ["monday", "tuesday", "wednesday"]

zipped_list = list(zip(food_list, calories_list, day_list))
print(zipped_list)
# Output: [('apple', 100, 'monday'), ('banana', 150, 'tuesday'), ('melon', 200, 'wednesday')]

```

### 🔴 Hard Example: Looping with `zip`

```python
for food, calorie in zip(food_list, calories_list):
    print(f"{food.capitalize()} has {calorie} calories.")
# Output:
# Apple has 100 calories.
# Banana has 150 calories.
# Melon has 200 calories.

```

---

### 4️⃣ `random` Module: Random Operations

We use the `random` module for operations like generating random numbers or shuffling lists.

### ✅ Generating a Random Number with `randint()`

The `randint(a, b)` function generates a random integer between `a` and `b` (inclusive).

```python
from random import randint
# Generates a random number between 0 and 100
print(randint(0, 100))

```

> 💡 Important Tip: When picking a random element from a list, it's best to use randint(0, len(my_list) - 1) because the last index is len(list) - 1. Otherwise, you might get an IndexError.
> 

### 🟡 Shuffling a List with `shuffle()`

The `shuffle()` function shuffles the elements of a list **in-place** (permanently).

```python
from random import shuffle
my_list = [10, 20, 30, 40, 50, 60, 70]
shuffle(my_list)
print(my_list)
# Output (Example): [40, 10, 70, 50, 20, 60, 30]

```

---

### 5️⃣ List Comprehension

A much shorter, more readable, and efficient way to create a new list using a loop.

### ✅ Easy Example: Simple Copying

A stylish alternative to the classic `for` loop.

```python
# Classic Method
new_list = []
my_string = "metallica"
for element in my_string:
    new_list.append(element)
print(new_list)
# Output: ['m', 'e', 't', 'a', 'l', 'l', 'i', 'c', 'a']

# List Comprehension Method
new_list_comp = [element for element in my_string]
print(new_list_comp)
# Output: ['m', 'e', 't', 'a', 'l', 'l', 'i', 'c', 'a']

```

### 🟡 Medium Example: Adding a Condition (`if`)

You can include only the elements that meet a specific condition in the new list.

```python
number_list = [10, 21, 30, 45, 50]
# Get only the even numbers
even_numbers = [num for num in number_list if num % 2 == 0]
print(even_numbers)
# Output: [10, 30, 50]

```

### 🔴Hard Example: Conditional Value Assignment (`if/else`)

You can assign a different value for each element based on a condition.

```python
number_list = [1, 2, 3, 4, 5]
# Add the number itself if it's even, or the text 'Odd Number' if it's odd
new_list = [num if num % 2 == 0 else "Odd Number" for num in number_list]
print(new_list)
# Output: ['Odd Number', 2, 'Odd Number', 4, 'Odd Number']

```
