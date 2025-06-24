# Python - [Sets]

---

# 🧮 Python'da Kümeler (Sets) ve Küme Metotları

Kümeler (Sets), içerisinde **tekrarlı eleman barındırmayan** ve elemanları **sırasız** olan koleksiyonlardır.

## 🔹 Temel Özellikleri:

- ✅ **Benzersiz (Unique):** Her eleman yalnızca bir kez bulunur.
- 🔀 **Sırasız (Unordered):** Elemanlara indeksle erişilemez; belirli bir sıraları yoktur.

---

## 📌 1. Küme Nasıl Oluşturulur?

### ✅ Listeden Küme Oluşturma (Tekrarları Temizleme)

Kümelerin en yaygın kullanım alanlarından biri, bir listedeki tekrarlı verileri **ayıklamaktır**. `set()` fonksiyonu bu işi kolayca yapar.

```python
# İçinde tekrar eden elemanlar olan bir liste
my_list = [10, 20, 30, 10, 20, 40, 10, 20, 40]

print(f"Listenin orijinal hali: {my_list}")
print(f"Listenin eleman sayısı: {len(my_list)}")

# Listeyi kümeye çeviriyoruz (tekrarlar silinir)
my_set = set(my_list)

print(f"Kümenin son hali: {my_set}")
print(f"Kümenin eleman sayısı: {len(my_set)}")

# Output:

# Listenin orijinal hali: [10, 20, 30, 10, 20, 40, 10, 20, 40]
# Listenin eleman sayısı: 9
# Kümenin son hali: {40, 10, 20, 30}
# Kümenin eleman sayısı: 4
```

📌 Not: Elde edilen kümenin elemanları sıralı görünmeyebilir. Bu tamamen Python’un set yapısının sırasız doğasından kaynaklanır.

---

### Doğrudan Küme Oluşturma

Kümeler, süslü parantezler `{}` arasına elemanlar yazılarak da oluşturulabilir. Tekrarlı yazılan elemanlar otomatik olarak teke indirilir.

```python
my_set = {10, 20, 30, 10, 20, 40}
print(my_set)
# Çıktı: {40, 10, 20, 30}

```

---

### 🚨 Önemli Uyarı: Boş Küme Oluşturma

Boş bir küme oluşturmak için `set()` fonksiyonunu kullanmalısınız. Boş süslü parantez `{}` kullanırsanız, Python bunu bir **sözlük (dictionary)** olarak algılar.

```python
# YANLIŞ YÖNTEM
empty_set = {}
print(type(empty_set))
# Çıktı: <class 'dict'>

# DOĞRU YÖNTEM
empty_set = set()
print(type(empty_set))
# Çıktı: <class 'set'>

```

---

### 2. Eleman Ekleme ve Çıkarma Metotları

### 📌 .add()

Kümeye yeni bir eleman ekler. Eğer eklenmek istenen eleman zaten kümede varsa, hiçbir değişiklik yapmaz.

```python
my_set = {10, 20, 30}
my_set.add(40) # Yeni eleman eklenir
print(my_set)
# Çıktı: {40, 10, 20, 30}

my_set.add(10) # 10 zaten var, küme değişmez
print(my_set)
# Çıktı: {40, 10, 20, 30}

```

### 📌 .update()

Kümeye başka bir küme, liste veya demet gibi birden çok eleman içeren bir koleksiyonu ekler.

```python
my_set = {10, 20}
my_set.update([20, 30, 40])
print(my_set)
# Çıktı: {40, 10, 20, 30}

```

### 📌 .remove()

Belirtilen elemanı kümeden siler. Eğer eleman kümede yoksa `KeyError` hatası verir.

```python
my_set = {10, 20, 30}
my_set.remove(20)
print(my_set)
# Çıktı: {10, 30}

```

### 📌 .discard()

`.remove()` gibidir, ancak eleman kümede olmasa bile hata vermez. Daha güvenli bir silme yöntemidir.

```python
my_set = {10, 20, 30}
my_set.discard(50) # 50 kümede yok, ama hata vermez
print(my_set)
# Çıktı: {10, 20, 30}

```

### 📌 .pop()

Kümeden **rastgele** bir elemanı siler ve sildiği elemanı döndürür. Kümeler sırasız olduğu için hangi elemanın silineceği belli değildir.

```python
my_set = {10, 20, 30}
silinen = my_set.pop()
print(f"Silinen eleman: {silinen}")
print(f"Kümenin yeni hali: {my_set}")

```

### 📌 .clear()

Kümenin içindeki tüm elemanları temizler.

```python
my_set = {10, 20, 30}
my_set.clear()
print(my_set)
# Çıktı: set()

```

---

### 3. Matematiksel Küme İşlemleri

Kümelerin asıl gücü, matematiksel küme operasyonlarını kolayca yapabilmeleridir.

```python
set1 = {10, 20, 30, 40, 50}
set2 = {30, 40, 50, 60, 70}

```

### 📌 Birleşim (Union)

İki kümenin tüm elemanlarını içeren yeni bir küme oluşturur. Hem `.union()` metodu hem de `|` operatörü kullanılabilir.

```python
# Yöntem 1: Metot ile
print(set1.union(set2))
# Çıktı: {70, 40, 10, 50, 20, 60, 30}

# Yöntem 2: Operatör ile
print(set1 | set2)
# Çıktı: {70, 40, 10, 50, 20, 60, 30}

```

### 📌 Kesişim (Intersection)

İki kümede de **ortak olarak bulunan** elemanları içeren yeni bir küme oluşturur. Hem `.intersection()` metodu hem de `&` operatörü kullanılabilir.

```python
# Yöntem 1: Metot ile
print(set1.intersection(set2))
# Çıktı: {40, 50, 30}

# Yöntem 2: Operatör ile
print(set1 & set2)
# Çıktı: {40, 50, 30}

```

### 📌 Fark (Difference)

İlk kümede olup ikinci kümede **olmayan** elemanları içeren yeni bir küme oluşturur. Hem `.difference()` metodu hem de `-` operatörü kullanılabilir.

```python
# set1'in set2'den farkı
print(set1.difference(set2)) # Çıktı: {10, 20}
print(set1 - set2)           # Çıktı: {10, 20}

# set2'nin set1'den farkı
print(set2.difference(set1)) # Çıktı: {60, 70}
print(set2 - set1)           # Çıktı: {60, 70}

```

### 📌 Simetrik Fark (Symmetric Difference)

İki kümenin kesişimi dışında kalan tüm elemanları içeren yeni bir küme oluşturur. Hem `.symmetric_difference()` metodu hem de `^` operatörü kullanılabilir.

```python
# Yöntem 1: Metot ile
print(set1.symmetric_difference(set2))
# Çıktı: {10, 20, 60, 70}

# Yöntem 2: Operatör ile
print(set1 ^ set2)
# Çıktı: {10, 20, 60, 70}

```

# For ENG

---

# 🧮 Sets in Python and Set Methods

Sets in Python are collections that **do not allow duplicate elements** and whose elements are **unordered**.

## 🔹 Key Features:

- ✅ **Unique:** Each element can appear only once in a set.
- 🔀 **Unordered:** Elements do not have a specific order and cannot be accessed via index.

---

## 📌 1. How to Create a Set?

### ✅ Creating a Set from a List (Removing Duplicates)

One of the most common uses of sets is to **remove duplicate values** from a list. The `set()` function easily converts a list into a set.

```python
# A list with repeated elements
my_list = [10, 20, 30, 10, 20, 40, 10, 20, 40]

print(f"Original list: {my_list}")
print(f"List length: {len(my_list)}")

# Convert the list into a set (removes duplicates)
my_set = set(my_list)

print(f"Set result: {my_set}")
print(f"Set length: {len(my_set)}")

# Output:
# Original list: [10, 20, 30, 10, 20, 40, 10, 20, 40]
# List length: 9
# Set result: {40, 10, 20, 30}
# Set length: 4

```

📌 **Note:** The resulting set may appear unordered. This is normal because sets in Python are unordered collections.

---

### Direct Set Creation

Sets can also be created directly by placing elements inside curly braces `{}`. Duplicates are automatically removed.

```python
my_set = {10, 20, 30, 10, 20, 40}
print(my_set)
# Output: {40, 10, 20, 30}

```

---

### 🚨 Important: Creating an Empty Set

To create an empty set, use the `set()` function. Using empty curly braces `{}` will create a **dictionary** instead of a set.

```python
# WRONG METHOD
empty_set = {}
print(type(empty_set))
# Output: <class 'dict'>

# CORRECT METHOD
empty_set = set()
print(type(empty_set))
# Output: <class 'set'>

```

---

## 📌 2. Adding and Removing Elements

### 📌 `.add()`

Adds a new element to the set. If the element already exists, the set remains unchanged.

```python
my_set = {10, 20, 30}
my_set.add(40)  # New element
print(my_set)
# Output: {40, 10, 20, 30}

my_set.add(10)  # 10 already exists
print(my_set)
# Output: {40, 10, 20, 30}

```

### 📌 `.update()`

Adds multiple elements (from a list, set, or tuple) to the set.

```python
my_set = {10, 20}
my_set.update([20, 30, 40])
print(my_set)
# Output: {40, 10, 20, 30}

```

### 📌 `.remove()`

Removes a specific element. If the element is not found, raises a `KeyError`.

```python
my_set = {10, 20, 30}
my_set.remove(20)
print(my_set)
# Output: {10, 30}

```

### 📌 `.discard()`

Similar to `.remove()`, but doesn’t raise an error if the element is missing. Safer option.

```python
my_set = {10, 20, 30}
my_set.discard(50)  # 50 not in set, no error
print(my_set)
# Output: {10, 20, 30}

```

### 📌 `.pop()`

Removes and returns a **random element** from the set. Since sets are unordered, the removed item is unpredictable.

```python
my_set = {10, 20, 30}
removed = my_set.pop()
print(f"Removed element: {removed}")
print(f"Updated set: {my_set}")

```

### 📌 `.clear()`

Removes all elements from the set.

```python
my_set = {10, 20, 30}
my_set.clear()
print(my_set)
# Output: set()

```

---

## 📌 3. Mathematical Set Operations

Sets shine in handling mathematical operations like union, intersection, and difference.

```python
set1 = {10, 20, 30, 40, 50}
set2 = {30, 40, 50, 60, 70}

```

### 📌 Union

Combines all unique elements from both sets.

```python
# Method 1: Using .union()
print(set1.union(set2))
# Output: {70, 40, 10, 50, 20, 60, 30}

# Method 2: Using | operator
print(set1 | set2)
# Output: {70, 40, 10, 50, 20, 60, 30}

```

### 📌 Intersection

Returns elements common to both sets.

```python
# Method 1: Using .intersection()
print(set1.intersection(set2))
# Output: {40, 50, 30}

# Method 2: Using & operator
print(set1 & set2)
# Output: {40, 50, 30}

```

### 📌 Difference

Returns elements that exist in the first set but not in the second.

```python
# Elements in set1 not in set2
print(set1.difference(set2))  # Output: {10, 20}
print(set1 - set2)            # Output: {10, 20}

# Elements in set2 not in set1
print(set2.difference(set1))  # Output: {60, 70}
print(set2 - set1)            # Output: {60, 70}

```

### 📌 Symmetric Difference

Returns elements that are in either set, but **not in both**.

```python
# Method 1: Using .symmetric_difference()
print(set1.symmetric_difference(set2))
# Output: {10, 20, 60, 70}

# Method 2: Using ^ operator
print(set1 ^ set2)
# Output: {10, 20, 60, 70}

```
