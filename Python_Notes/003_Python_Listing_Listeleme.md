# Pyton -[Listing]

# ⛓️ Python'da Listeler ve Liste Metotları

Listeler, farklı veri tiplerini bir arada tutabilen, sıralı ve **değiştirilebilir (mutable)** koleksiyonlardır. Python'da en çok kullanılan veri yapılarından biridir.

---

## 📌 1. Liste Nedir ve Nasıl Oluşturulur?

Bir liste, köşeli parantezler `[]` içine virgülle ayrılmış elemanlar yazılarak oluşturulur.

```python
# Örnek listemizi oluşturalım
my_list = [17, 27, 18]
print(my_list)
# Çıktı: [17, 27, 18]

```

---

## 📌 2. Listelerin Değişebilirliği (Mutability)

String'lerin aksine, listeler **değiştirilebilir**. Yani bir liste oluşturduktan sonra elemanlarını güncelleyebilir, silebilir veya yeni elemanlar ekleyebilirsiniz. Bu, listelerin en önemli özelliğidir.

```python
my_list = [17, 27, 18]
# 0. indeksteki elemanı güncelleyelim
my_list[0] = 99
print(my_list)
# Çıktı: [99, 27, 18]

```

## 🧩 Nested Lists (İç İçe Listeler)

Bir listenin elemanı başka bir liste olabilir. Bu yapıya **iç içe liste (nested list)** denir. İçteki listeye ulaşmak için birden fazla köşeli parantez kullanılır.

```python
nested_list = [10, 20, ["a", "b", "c"], 50]

# İçteki listenin tamamına erişim
print(nested_list[2])
# Çıktı: ['a', 'b', 'c']

# İçteki listenin 'b' elemanına erişim
print(nested_list[2][1])
# Çıktı: 'b'

```

---

## 💡 Pratik Kullanım: Kullanıcı Girdisi ve Tip Dönüşümü

`input()` fonksiyonu ile kullanıcıdan alınan her veri **string (metin)** olarak gelir. Bu veriyi sayısal işlemlerde kullanmak için `int()` veya `float()` ile **tip dönüşümü** yapmak gerekir.

```python
# Kullanıcıdan alınan değer '20' (string)
deger = '20'

# Sayıya çevirip işlem yapıyoruz
sonuc = int(deger) * 2
print(sonuc)
# Çıktı: 40

```

```python
# Ondalıklı sayıya çevirme örneği:
deger = "12.5"
sonuc = float(deger) + 7.5
print(sonuc)
# Çıktı: 20.0

```

📌 Not: `int()` yalnızca tam sayı string'leri dönüştürebilir. Noktalı sayılar için `float()` kullanılır.

---

## 📌 3. Liste Metotları Kataloğu

Aşağıda `my_list` üzerinden tüm liste metotlarının açıklamaları ve örnekleri bulunmaktadır.

---

### 🔹 .append()

Listenin **sonuna** yeni bir eleman ekler.

```python
my_list = [17, 27, 18]
my_list.append(50)
print(my_list)
# Çıktı: [17, 27, 18, 50]

```

---

### 🔹 .insert()

Belirtilen indekse yeni bir eleman ekler, diğer elemanları sağa kaydırır.

```python
my_list = [17, 27, 18]
my_list.insert(1, 99)
print(my_list)
# Çıktı: [17, 99, 27, 18]

```

---

### 🔹 .extend()

Bir listeyi, başka bir listenin elemanlarıyla genişletir.

```python
my_list = [17, 27, 18]
eklenecek_liste = [1, 2, 3]
my_list.extend(eklenecek_liste)
print(my_list)
# Çıktı: [17, 27, 18, 1, 2, 3]

```

---

### 🔹 .pop()

Belirtilen indeksteki elemanı **listeden kaldırır ve döndürür**. İndeks verilmezse, en sondakini kaldırır.

```python
my_list = [17, 27, 18, 50]

kaldirilan = my_list.pop()
print(f"Kaldırılan: {kaldirilan}")
print(f"Güncel Liste: {my_list}")

my_list.pop(0)
print(my_list)
# Çıktı: [27, 18]

```

---

### 🔹 .remove()

Belirtilen **değere sahip ilk elemanı** listeden kaldırır.

```python
my_list = [17, 27, 18, 27]
my_list.remove(27)
print(my_list)
# Çıktı: [17, 18, 27]

```

---

### 🔹 .sort()

Listeyi **küçükten büyüğe** sıralar.

```python
my_list = [17, 27, 18, 5]
my_list.sort()
print(my_list)
# Çıktı: [5, 17, 18, 27]

# Tersten sıralama
my_list.sort(reverse=True)
print(my_list)
# Çıktı: [27, 18, 17, 5]

```

---

### 🔹 .reverse()

Listenin sırasını **tersine çevirir**.

```python
my_list = [17, 27, 18]
my_list.reverse()
print(my_list)
# Çıktı: [18, 27, 17]

```

---

### 🔹 .count()

Belirtilen değerin kaç kez geçtiğini sayar.

```python
my_list = [17, 27, 18, 27, 27]
print(my_list.count(27))
# Çıktı: 3

```

---

### 🔹 .index()

Belirtilen değerin **ilk görüldüğü** indeksini verir.

```python
my_list = [17, 27, 18]
print(my_list.index(18))
# Çıktı: 2

```

---

### 🔹 .copy()

Listenin sığ bir kopyasını döner.

```python
my_list = [17, 27, 18]
kopya = my_list.copy()
kopya.append(99)

print(f"Orijinal: {my_list}")
print(f"Kopya: {kopya}")

```

---

### 🔹 .clear()

Listedeki tüm elemanları siler.

```python
my_list = [17, 27, 18]
my_list.clear()
print(my_list)
# Çıktı: []

```

---

# For Eng

# ⛓️ Lists and List Methods in Python

Lists are **ordered and mutable** collections that can hold elements of different data types. They are one of the most used data structures in Python.

---

## 📌 1. What is a List and How to Create One?

A list is created using square brackets `[]` with elements separated by commas.

```python
# Let's create our example list
my_list = [17, 27, 18]
print(my_list)
# Output: [17, 27, 18]

```

---

## 📌 2. List Mutability

Unlike strings, lists are **mutable**. This means you can update, delete, or add new elements after creating a list. This is one of the most important properties of lists.

```python
my_list = [17, 27, 18]
# Let's update the element at index 0
my_list[0] = 99
print(my_list)
# Output: [99, 27, 18]

```

## 🧩 Nested Lists

An element in a list can be another list. This structure is called a **nested list**. To access the inner list or its elements, use an additional pair of square brackets.

```python
nested_list = [10, 20, ["a", "b", "c"], 50]

# Access the entire inner list
print(nested_list[2])
# Output: ['a', 'b', 'c']

# Access the element 'b' inside the inner list
print(nested_list[2][1])
# Output: 'b'

```

---

## 💡 Practical Use: User Input and Type Conversion

The `input()` function always returns user input as a **string**. To use this input in mathematical operations, you must convert it using `int()` or `float()`.

```python
# The value '20' received from the user is a string
deger = '20'

# Convert to number and multiply
sonuc = int(deger) * 2
print(sonuc)
# Output: 40

```

```python
# Example of converting to a floating point number
deger = "12.5"
sonuc = float(deger) + 7.5
print(sonuc)
# Output: 20.0

```

📌 Note: `int()` can only convert integer strings. For decimal numbers, use `float()`.

---

## 📌 3. List Methods Catalog

Below are explanations and examples of all common list methods using `my_list`.

---

### 🔹 .append()

Adds a new element to the **end** of the list.

```python
my_list = [17, 27, 18]
my_list.append(50)
print(my_list)
# Output: [17, 27, 18, 50]

```

---

### 🔹 .insert()

Inserts a new element at the specified index and shifts the other elements to the right.

```python
my_list = [17, 27, 18]
my_list.insert(1, 99)
print(my_list)
# Output: [17, 99, 27, 18]

```

---

### 🔹 .extend()

Extends a list by appending elements from another list.

```python
my_list = [17, 27, 18]
eklenecek_liste = [1, 2, 3]
my_list.extend(eklenecek_liste)
print(my_list)
# Output: [17, 27, 18, 1, 2, 3]

```

---

### 🔹 .pop()

**Removes and returns** the element at the specified index. If no index is provided, removes the last element.

```python
my_list = [17, 27, 18, 50]

kaldirilan = my_list.pop()
print(f"Removed: {kaldirilan}")
print(f"Updated List: {my_list}")

my_list.pop(0)
print(my_list)
# Output: [27, 18]

```

---

### 🔹 .remove()

Removes the **first occurrence** of the specified value.

```python
my_list = [17, 27, 18, 27]
my_list.remove(27)
print(my_list)
# Output: [17, 18, 27]

```

---

### 🔹 .sort()

Sorts the list in **ascending order**.

```python
my_list = [17, 27, 18, 5]
my_list.sort()
print(my_list)
# Output: [5, 17, 18, 27]

# Sort in descending order
my_list.sort(reverse=True)
print(my_list)
# Output: [27, 18, 17, 5]

```

---

### 🔹 .reverse()

**Reverses** the order of the list.

```python
my_list = [17, 27, 18]
my_list.reverse()
print(my_list)
# Output: [18, 27, 17]

```

---

### 🔹 .count()

Counts how many times a value appears in the list.

```python
my_list = [17, 27, 18, 27, 27]
print(my_list.count(27))
# Output: 3

```

---

### 🔹 .index()

Returns the **index of the first occurrence** of the specified value.

```python
my_list = [17, 27, 18]
print(my_list.index(18))
# Output: 2

```

---

### 🔹 .copy()

Returns a **shallow copy** of the list.

```python
my_list = [17, 27, 18]
kopya = my_list.copy()
kopya.append(99)

print(f"Original: {my_list}")
print(f"Copy: {kopya}")

```

---

### 🔹 .clear()

Removes all elements from the list.

```python
my_list = [17, 27, 18]
my_list.clear()
print(my_list)
# Output: []

```